# Charting in Colaboratory

A common use for notebooks is data visualization using charts. Colaboratory makes this easy with several charting tools available as Python imports.

## Matplotlib

[Matplotlib](http://matplotlib.org/) is the most common charting package, see its [documentation](http://matplotlib.org/api/pyplot_api.html) for details, and its [examples](http://matplotlib.org/gallery.html#statistics) for inspiration.

### Line Plots


```
import matplotlib.pyplot as plt
 
x  = [1, 2, 3, 4, 5, 6, 7, 8, 9]
y1 = [1, 3, 5, 3, 1, 3, 5, 3, 1]
y2 = [2, 4, 6, 4, 2, 4, 6, 4, 2]
plt.plot(x, y1, label="line L")
plt.plot(x, y2, label="line H")
plt.plot()

plt.xlabel("x axis")
plt.ylabel("y axis")
plt.title("Line Graph Example")
plt.legend()
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_3_0.png)
    


### Bar Plots


```
import matplotlib.pyplot as plt

plt.style.use('default')
plt.rcParams['figure.figsize'] = (6, 5)
plt.rcParams['font.size'] = 12

x = [1, 2, 3]
y = [1, 2, 3]

fig, ((ax1, ax2), (ax3, ax4)) = plt.subplots(2, 2)

ax1.bar(x, y, color='aquamarine', edgecolor='black', hatch='/')
ax2.bar(x, y, color='salmon', edgecolor='black', hatch='\\')
ax3.bar(x, y, color='navajowhite', edgecolor='black', hatch='+')
ax4.bar(x, y, color='lightskyblue', edgecolor='black', hatch='*')

plt.tight_layout()
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_5_0.png)
    



```
import matplotlib.pyplot as plt
from matplotlib.patches import Ellipse, Polygon

fig = plt.figure()
ax1 = fig.add_subplot(111)
# draw hatch
ax1.bar(range(1, 5), range(1, 5), color='none', edgecolor='red', hatch="/", lw=1., zorder = 0)
# draw edge
ax1.bar(range(1, 5), range(1, 5), color='none', edgecolor='k', zorder=1, lw=2.)

#ax1.set_xticks([1.5, 2.5, 3.5, 4.5])
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_6_0.png)
    



```
import pandas as pd
import matplotlib.pyplot as plt

employees=["Rudra","Alok","Prince","Nayan","Reman"]
earnings={
    "January":[0,20,15,18,14],
    "February":[0,13,10,18,15],
    "March":[40,20,10,15,18],
}

df=pd.DataFrame(earnings,index=employees)

df.plot(kind="barh",stacked=True,figsize=(10,8))


plt.legend(loc="lower left",bbox_to_anchor=(0.8,1.0))
fig, ax = plt.subplots(1,1,figsize=(10,5))
ax.spines['right'].set_visible(False)
ax.spines['top'].set_visible(False)
#ax.spines['left'].set_visible(False)
ax.spines['bottom'].set_visible(False)
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_7_0.png)
    



    
![png](Charts_Colab_files/Charts_Colab_7_1.png)
    



```
import numpy as np 
import matplotlib.pyplot as plt 
   
labels = ['Detail of TLSRPT using HTTPS','HTTPS','Detail of TLSRPT using Email','Email',  'Wellformed', 'Normal Response'] 
   
mine = [0,10,0,722, 730, 747] 
other_1 = [0, 0, 692, 0,0,0] 
other_2 = [0, 0, 27, 0,0,0] 
others = [0,0,720,0,0,0]
other_3 = [0, 0, 3, 0,0,0] 
others2 = [0,0,723,0,0,0]
other_4 = [3, 0, 3, 0,0,0] 
HTTPS = [8, 0, 0, 0,0,0] 

width = 0.3
   
fig, ax = plt.subplots(1,1,figsize=(10,5))
ax.xaxis.tick_top()
   
bar = ax.barh(labels, mine, width, color='none',hatch='xxxxx',edgecolor='k', lw=1, zorder = 0.3) 
for rect in bar:
    witdh = rect.get_width()
    posx = witdh * 1.01
    posy = rect.get_y() + rect.get_height() * 0.5 -0.04
    if rect.get_width() != 0:
      ax.text(posx, posy, ' %d (%.2f%%)' % (witdh,witdh/747*100), rotation=0, ha='left', va='center')

ax.barh(labels, other_1, width, left = mine, label ='Counts of using One-Email Address (Ratio): 693 (92.77%)',color='none',hatch='...',edgecolor='dodgerblue', lw=1, zorder = 0.3) 

ax.barh(labels, other_2, width, left = other_1, label ='Counts of using Two-Email Address (Ratio): 27 (3.61%)') 

ax.barh(labels, other_3, width, left = others, label ='Counts of using Three-Email Address (Ratio): 1 (0.13%)') 

ax.barh(labels, other_4, width, left = others2, label ='Counts of using Email with HTTPS (Ratio): 2 (0.27%)') 

ax.barh(labels, HTTPS, width, left = other_4, label ='Counts of using HTTPS (Ratio): 7 (1.07%)') 
 
ax.legend() 
ax.spines['right'].set_visible(False)
ax.spines['top'].set_visible(False)
#ax.spines['left'].set_visible(False)
ax.spines['bottom'].set_visible(False)
ax.set_title('Analysis the method of TLSRPT') 
box = ax.get_position() # 범례를 그래프상자 밖에 그리기위해 상자크기를 조절
ax.set_position([box.x0, box.y0, box.width, box.height])
ax.legend(frameon=False, bbox_to_anchor=(1,0), shadow=True, ncol=1)   
plt.show() 
```


    
![png](Charts_Colab_files/Charts_Colab_8_0.png)
    



```
import numpy as np
import matplotlib.pyplot as plt

h = [8,2,1,27, 693, 721, 731,747]
h1 = h[:4]
h2 = h[4:]
r = ['8 (1.07%)','2 (0.27%)','1 (0.13%)', '27 (3.61%)', '693 (92.77%)', '721 (96.52%)', '731 (97.86%)','747 (100.00%)']
r1 = r[:4]
r2 = r[4:]
fig, ax = plt.subplots(1,1,figsize=(10,5))
h = np.array(h)
plt.gca().use_sticky_edges = False
plt.barh(r, width=h, left=(h.max() - h) / 2, align='center', color='white',edgecolor='black')
for ri in r2:
    plt.text(h.max() /2, ri, ri, ha='center', va='center', color='black', size=10)
for ri in r1:
    plt.text(h.max() /2, ri, ri, ha='center', va='center', color='black', size=10)
plt.yticks(np.arange(8),['HTTPS','Email-with-HTTPS','Three email address','Two email address','One email address','Email','Wellformed','Normal Response']) # optionally remove standard y ticks and their labels
ax.spines['right'].set_visible(False)
ax.spines['top'].set_visible(False)
#ax.spines['left'].set_visible(False)
ax.spines['bottom'].set_visible(False)
ax.get_xaxis().set_visible(False)
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_9_0.png)
    



```
import numpy as np
import matplotlib.pyplot as plt

women_pop = np.array([5., 30., 45., 22.])
men_pop     = np.array( [5., 25., 50., 20.])
X = np.arange(4)

plt.barh(X, women_pop, color = 'r')
plt.barh(X, -men_pop, color = 'b')
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_10_0.png)
    



```
import numpy as np

def compute_pos(yticks, height, i, models):
  index = np.arange(len(yticks))
  n = len(models)
  correction = i - 0.5*(n-1)
  return index + height * correction

import matplotlib.pyplot as plt
models = ['Scanned', 'model B', 'model C']
yticks = ['STARTTLS', 'DNSSEC']
data = {
    'Scanned':[0.21, 0],
    'model D':[0.65, 895540],
    'model B':[0.61, 747],
    'model C':[0.55, 894793]
    }
height = 0.15

fig, ax = plt. subplots(1,1,figsize=(10,3))
ax.xaxis.tick_top()
ax.set_yticks(range(len(yticks)))
ax.set_yticklabels(yticks, fontsize=10)	

pos0 = compute_pos(yticks, height, 0, models)
print(pos0)
bar = ax.barh(pos0, data['model D'], height=height*0.95, label='model D', color='none',hatch='xxxxx',edgecolor='dodgerblue', lw=3., zorder = 1)
present_width(ax, bar) # bar너비 출력

pos1 = compute_pos(yticks, height, 1, models)
bar = ax.barh(pos1, data['model C'], height=height*0.95, label='model D', color='none',hatch='xxxxx',edgecolor='dodgerblue', lw=3., zorder = 1)
present_width(ax, bar) # bar너비 출력

pos2 = compute_pos(yticks, height, 2, models)
bar = ax.barh(pos2, data['model B'], height=height*0.95, label='model D', color='none',hatch='xxxxx',edgecolor='dodgerblue', lw=3., zorder = 1)
present_width(ax, bar) # bar너비 출력
print(pos0,pos1,pos2)
# for i, model in enumerate(models):
#   pos = compute_pos(yticks, height, i, models)
#   bar = ax.barh(pos, data[model], height=height*0.95, label=model, color='none',hatch='xxxxx',edgecolor='dodgerblue', lw=3., zorder = 1)
#   present_width(ax, bar) # bar너비 출력

box = ax.get_position() # 범례를 그래프상자 밖에 그리기위해 상자크기를 조절
ax.set_position([box.x0, box.y0, box.width, box.height])
ax.legend(frameon=False, bbox_to_anchor=(0.65,0), shadow=True, ncol=3)
	
ax.spines['right'].set_visible(False)
ax.spines['top'].set_visible(False)
ax.spines['left'].set_visible(False)
ax.spines['bottom'].set_visible(False)
ax.set_axisbelow(True)
ax.xaxis.grid(True, color='gray', linestyle=(0, (5, 10)), linewidth=0.5)
```

    [-0.15  0.85]
    [-0.15  0.85] [0. 1.] [0.15 1.15]



    
![png](Charts_Colab_files/Charts_Colab_11_1.png)
    



```

```


```
import numpy as np

def compute_pos(yticks, height, i, models):
  index = np.arange(len(yticks))
  n = len(models)
  correction = i - 0.5*(n-1)
  return index + height * correction

import matplotlib.pyplot as plt
yticks = ['STARTTLS', 'DNSSEC', 'Request: _smtp.tls.domain']
data = {
    'model D':[0.65, 1, 1],
    'model C':[0.55, 1, 1],
    'model B':[0.61, 2, 1]
    }
height = 2

fig, ax = plt. subplots(1,1,figsize=(10,2))
ax.xaxis.tick_top()
#ax.xaxis.set_label_position('top')
ax.set_yticks(range(len(yticks)))
ax.set_yticklabels(yticks, fontsize=10)

#pos_2 = compute_pos(yticks, height, 10, 'model D')
bar = ax.barh(5, data['model D'], height=2, label='Count of Scanned Domain', color='none',hatch='xxxxx',edgecolor='dodgerblue', lw=1, zorder = 0.3)
present_width(ax, bar) # bar너비 출력

#pos_1 = compute_pos(yticks, height, 5, 'model C')
bar = ax.barh(3, data['model C'], height=1, label='No Response (Ratio)', color='none',hatch='....',edgecolor='red', lw=1, zorder = 0.3)
present_width(ax, bar) # bar너비 출력

#pos_0 = compute_pos(yticks, height, 0, 'model B')
bar = ax.barh(1, data['model B'], height=0, label='Yes Response (Ratio)', color='none',hatch='xxxxx',edgecolor='green', lw=1., zorder = 0.3)
present_width(ax, bar) # bar너비 출력


box = ax.get_position() # 범례를 그래프상자 밖에 그리기위해 상자크기를 조절
ax.set_position([box.x0, box.y0, box.width , box.height])
ax.legend(frameon=False, bbox_to_anchor=(0.65,0), shadow=True, ncol=3)

ax.spines['right'].set_visible(False)
ax.spines['top'].set_visible(False)
ax.spines['left'].set_visible(False)
ax.spines['bottom'].set_visible(False)
ax.set_axisbelow(True)
ax.xaxis.grid(True, color='gray', linestyle=(0, (5, 10)), linewidth=0.5)
```


    
![png](Charts_Colab_files/Charts_Colab_13_0.png)
    



```
def compute_pos(yticks, height, i, models):
  index = np.arange(len(yticks))
  n = len(models)
  correction = i - 0.2*(n-1)
  return index + height * correction

def present_width(ax, bar):
	for rect in bar:
		witdh = rect.get_width()
		posx = witdh*1.01
		posy = rect.get_y()+rect.get_height()*0.5
		ax.text(posx, posy, '%.3d' % witdh, rotation=0, ha='left', va='center')

import matplotlib.pyplot as plt
yticks = ['STARTTLS', 'DNSSEC', 'Request: _smtp.tls.domain']
data = {
    'model D':[0.65, 0.71, 895540],
    'model C':[0.55, 0.66, 894793],
    'model B':[0.61, 0.65, 747]
    }
height = 0.15

fig, ax = plt. subplots(1,1,figsize=(10,5))
ax.xaxis.tick_top()
#ax.xaxis.set_label_position('top')
ax.set_yticks(range(len(yticks)))
ax.set_yticklabels(yticks, fontsize=10)	
#for i, model in enumerate(models):

pos_2 = compute_pos(yticks, height, 2, 'model D')
bar = ax.barh(pos_2, data['model D'], height=height*0.65, label='Count of Scanned Domain', color='none',hatch='xxxxx',edgecolor='dodgerblue', lw=1, zorder = 0.3)
present_width(ax, bar) # bar너비 출력

pos_1 = compute_pos(yticks, height, 1, 'model C')
bar = ax.barh(pos_1, data['model C'], height=height*0.65, label='No Response (Ratio)', color='none',hatch='....',edgecolor='red', lw=1, zorder = 0.3)
present_width(ax, bar) # bar너비 출력

pos_0 = compute_pos(yticks, height, 0, 'model B')
bar = ax.barh(pos_0, data['model B'], height=height*0.65, label='Yes Response (Ratio)', color='none',hatch='xxxxx',edgecolor='green', lw=1., zorder = 0.3)
present_width(ax, bar) # bar너비 출력

box = ax.get_position() # 범례를 그래프상자 밖에 그리기위해 상자크기를 조절
ax.set_position([box.x0, box.y0, box.width * 0.9, box.height])
ax.legend(frameon=False, bbox_to_anchor=(1,0), shadow=True, ncol=3)	

ax.spines['right'].set_visible(False)
ax.spines['top'].set_visible(False)
ax.spines['left'].set_visible(False)
ax.spines['bottom'].set_visible(False)
ax.set_axisbelow(True)
ax.xaxis.grid(True, color='gray', linestyle=(0, (5, 10)), linewidth=0.5)
```


    
![png](Charts_Colab_files/Charts_Colab_14_0.png)
    



```
import matplotlib.pyplot as plt
import numpy as np

# plt.rcParams['xtick.bottom'] = plt.rcParams['xtick.labelbottom'] = False
# plt.rcParams['xtick.top'] = plt.rcParams['xtick.labeltop'] = True

x = np.arange(10)

fig, ax = plt.subplots()

ax.plot(x)
#ax.set_xlabel('xlabel top')  # Note title moves to make room for ticks

secax = ax.secondary_xaxis('top')
secax.set_xlabel('new label top')

plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_15_0.png)
    



```
import matplotlib.pyplot as plt
import numpy as np

def main():
  
	#### 1. bar plot으로 나타낼 데이터 입력
	models = ['model A', 'model B', 'model C', 'model D']
	yticks = ['Breast', 'Liver', 'Brain']
	data = {'model A':[0.65, 0.71, 0.69],
	        'model B':[0.61, 0.65, 0.64],
			'model C':[0.55, 0.66, 0.60],
			'model D':[0.60, 0.62, 0.57]}
	
	#### 2. matplotlib의 figure 및 axis 설정
	fig, ax = plt.subplots(1,1,figsize=(7,5)) # 1x1 figure matrix 생성, 가로(7인치)x세로(5인치) 크기지정
	colors = ['salmon', 'orange', 'cadetblue', 'skyblue']
	height = 0.15
	
	#### 3. bar 그리기
	for i, model in enumerate(models):
		pos = compute_pos(yticks, height, i, models)
		bar = ax.barh(pos, data[model], height=height*0.95, label=model, color='none',hatch='xxxxx',edgecolor='dodgerblue', lw=1., zorder = 0)
		bar = ax.barh(pos, data[model], height=height*0.95, label=model, color='none', edgecolor='k', zorder=1, lw=2.)
		present_width(ax, bar) # bar너비 출력
	
	#### 4. x축 세부설정
	ax.set_xlim([0.5,0.76])
	ax.set_xticks([0.5, 0.55, 0.6, 0.65, 0.7, 0.75])
	ax.xaxis.set_tick_params(labelsize=10)
  # secax = ax.secondary_xaxis('top')
  # secax.set_xlabel('new label top')
  #ax.set_xlabel('Prediction Accuracy', fontsize=14)
	
	#### 5. y축 세부설정
	ax.set_yticks(range(len(yticks)))
	ax.set_yticklabels(yticks, fontsize=10)	
	#ax.set_ylabel('Cancer type', fontsize=14)
	
	#### 6. 범례 나타내기
	box = ax.get_position() # 범례를 그래프상자 밖에 그리기위해 상자크기를 조절
	ax.set_position([box.x0, box.y0, box.width * 0.9, box.height])
	ax.legend(loc='center left', bbox_to_anchor=(1,0.5), shadow=True, ncol=1)
	
	#### 7. 보조선(눈금선) 나타내기
	ax.set_axisbelow(True)
	ax.xaxis.grid(True, color='gray', linestyle=(0, (5, 10)), linewidth=0.5)
  
	
	#### 8. 그래프 저장하고 출력하기
	plt.savefig('ex_barhplot.png', format='png', dpi=300)
	plt.show()
	
def compute_pos(yticks, height, i, models):
  index = np.arange(len(yticks))
  n = len(models)
  correction = i - 0.5*(n-1)
  return index + height * correction


		
if __name__=='__main__':
	main()
```


    
![png](Charts_Colab_files/Charts_Colab_16_0.png)
    



```
import matplotlib.pyplot as plt

# Look at index 4 and 6, which demonstrate overlapping cases.
x1 = [1, 3, 4, 5, 6, 7, 9]
y1 = [4, 7, 2, 4, 7, 8, 3]

x2 = [2, 4, 6, 8, 10]
y2 = [5, 6, 2, 6, 2]

# Colors: https://matplotlib.org/api/colors_api.html

plt.bar(x1, y1, label="Blue Bar", color='b')
plt.bar(x2, y2, label="Green Bar", color='g')
plt.plot()

plt.xlabel("bar number")
plt.ylabel("bar height")
plt.title("Bar Chart Example")
plt.legend()
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_17_0.png)
    


### Histograms


```
import matplotlib.pyplot as plt
import numpy as np

# Use numpy to generate a bunch of random data in a bell curve around 5.
n = 5 + np.random.randn(1000)

m = [m for m in range(len(n))]
plt.bar(m, n)
plt.title("Raw Data")
plt.show()

plt.hist(n, bins=20)
plt.title("Histogram")
plt.show()

plt.hist(n, cumulative=True, bins=20)
plt.title("Cumulative Histogram")
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_19_0.png)
    



    
![png](Charts_Colab_files/Charts_Colab_19_1.png)
    



    
![png](Charts_Colab_files/Charts_Colab_19_2.png)
    


### Scatter Plots


```
import matplotlib.pyplot as plt

x1 = [2, 3, 4]
y1 = [5, 5, 5]

x2 = [1, 2, 3, 4, 5]
y2 = [2, 3, 2, 3, 4]
y3 = [6, 8, 7, 8, 7]

# Markers: https://matplotlib.org/api/markers_api.html

plt.scatter(x1, y1)
plt.scatter(x2, y2, marker='v', color='r')
plt.scatter(x2, y3, marker='^', color='m')
plt.title('Scatter Plot Example')
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_21_0.png)
    


### Stack Plots


```
import matplotlib.pyplot as plt

idxes = [ 1,  2,  3,  4,  5,  6,  7,  8,  9]
arr1  = [23, 40, 28, 43,  8, 44, 43, 18, 17]
arr2  = [17, 30, 22, 14, 17, 17, 29, 22, 30]
arr3  = [15, 31, 18, 22, 18, 19, 13, 32, 39]

# Adding legend for stack plots is tricky.
plt.plot([], [], color='r', label = 'D 1')
plt.plot([], [], color='g', label = 'D 2')
plt.plot([], [], color='b', label = 'D 3')

plt.stackplot(idxes, arr1, arr2, arr3, colors= ['r', 'g', 'b'])
plt.title('Stack Plot Example')
plt.legend()
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_23_0.png)
    


### Pie Charts


```
import matplotlib.pyplot as plt

labels = 'S1', 'S2', 'S3'
sections = [56, 66, 24]
colors = ['c', 'g', 'y']

plt.pie(sections, labels=labels, colors=colors,
        startangle=90,
        explode = (0, 0.1, 0),
        autopct = '%1.2f%%')

plt.axis('equal') # Try commenting this out.
plt.title('Pie Chart Example')
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_25_0.png)
    


### fill_between and alpha


```
import matplotlib.pyplot as plt
import numpy as np

ys = 200 + np.random.randn(100)
x = [x for x in range(len(ys))]

plt.plot(x, ys, '-')
plt.fill_between(x, ys, 195, where=(ys > 195), facecolor='g', alpha=0.6)

plt.title("Fills and Alpha Example")
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_27_0.png)
    


### Subplotting using Subplot2grid


```
import matplotlib.pyplot as plt
import numpy as np

def random_plots():
  xs = []
  ys = []
  
  for i in range(20):
    x = i
    y = np.random.randint(10)
    
    xs.append(x)
    ys.append(y)
  
  return xs, ys

fig = plt.figure()
ax1 = plt.subplot2grid((5, 2), (0, 0), rowspan=1, colspan=2)
ax2 = plt.subplot2grid((5, 2), (1, 0), rowspan=3, colspan=2)
ax3 = plt.subplot2grid((5, 2), (4, 0), rowspan=1, colspan=1)
ax4 = plt.subplot2grid((5, 2), (4, 1), rowspan=1, colspan=1)

x, y = random_plots()
ax1.plot(x, y)

x, y = random_plots()
ax2.plot(x, y)

x, y = random_plots()
ax3.plot(x, y)

x, y = random_plots()
ax4.plot(x, y)

plt.tight_layout()
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_29_0.png)
    


## Plot styles

Colaboratory charts use [Seaborn's](https://seaborn.pydata.org) custom styling by default. To customize styling further please see the [matplotlib docs](https://matplotlib.org/users/style_sheets.html).

## 3D Graphs

### 3D Scatter Plots


```
import matplotlib.pyplot as plt
import numpy as np
from mpl_toolkits.mplot3d import axes3d

fig = plt.figure()
ax = fig.add_subplot(111, projection = '3d')

x1 = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
y1 = np.random.randint(10, size=10)
z1 = np.random.randint(10, size=10)

x2 = [-1, -2, -3, -4, -5, -6, -7, -8, -9, -10]
y2 = np.random.randint(-10, 0, size=10)
z2 = np.random.randint(10, size=10)

ax.scatter(x1, y1, z1, c='b', marker='o', label='blue')
ax.scatter(x2, y2, z2, c='g', marker='D', label='green')

ax.set_xlabel('x axis')
ax.set_ylabel('y axis')
ax.set_zlabel('z axis')
plt.title("3D Scatter Plot Example")
plt.legend()
plt.tight_layout()
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_33_0.png)
    


### 3D Bar Plots


```
import matplotlib.pyplot as plt
import numpy as np

fig = plt.figure()
ax = fig.add_subplot(111, projection = '3d')

x = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
y = np.random.randint(10, size=10)
z = np.zeros(10)

dx = np.ones(10)
dy = np.ones(10)
dz = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

ax.bar3d(x, y, z, dx, dy, dz, color='g')

ax.set_xlabel('x axis')
ax.set_ylabel('y axis')
ax.set_zlabel('z axis')
plt.title("3D Bar Chart Example")
plt.tight_layout()
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_35_0.png)
    


### Wireframe Plots


```
import matplotlib.pyplot as plt

fig = plt.figure()
ax = fig.add_subplot(111, projection = '3d')

x, y, z = axes3d.get_test_data()

ax.plot_wireframe(x, y, z, rstride = 2, cstride = 2)

plt.title("Wireframe Plot Example")
plt.tight_layout()
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_37_0.png)
    


## Seaborn

There are several libraries layered on top of Matplotlib that you can use in Colab. One that is worth highlighting is [Seaborn](http://seaborn.pydata.org):


```
import matplotlib.pyplot as plt
import numpy as np
import seaborn as sns

# Generate some random data
num_points = 20
# x will be 5, 6, 7... but also twiddled randomly
x = 5 + np.arange(num_points) + np.random.randn(num_points)
# y will be 10, 11, 12... but twiddled even more randomly
y = 10 + np.arange(num_points) + 5 * np.random.randn(num_points)
sns.regplot(x, y)
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_39_0.png)
    


That's a simple scatterplot with a nice regression line fit to it, all with just one call to Seaborn's [regplot](http://seaborn.pydata.org/generated/seaborn.regplot.html#seaborn.regplot).

Here's a Seaborn [heatmap](https://seaborn.pydata.org/generated/seaborn.heatmap.html):


```
import matplotlib.pyplot as plt
import numpy as np

# Make a 10 x 10 heatmap of some random data
side_length = 10
# Start with a 10 x 10 matrix with values randomized around 5
data = 5 + np.random.randn(side_length, side_length)
# The next two lines make the values larger as we get closer to (9, 9)
data += np.arange(side_length)
data += np.reshape(np.arange(side_length), (side_length, 1))
# Generate the heatmap
sns.heatmap(data)
plt.show()
```


    
![png](Charts_Colab_files/Charts_Colab_41_0.png)
    


## Altair

[Altair](http://altair-viz.github.io) is a declarative visualization library for creating interactive visualizations in Python, and is installed and enabled in Colab by default.

For example, here is an interactive scatter plot:


```
import altair as alt
from vega_datasets import data
cars = data.cars()

alt.Chart(cars).mark_point().encode(
    x='Horsepower',
    y='Miles_per_Gallon',
    color='Origin',
).interactive()
```





<div id="altair-viz-1"></div>
<script type="text/javascript">
  (function(spec, embedOpt){
    const outputDiv = document.getElementById("altair-viz-1");
    const paths = {
      "vega": "https://cdn.jsdelivr.net/npm//vega@5?noext",
      "vega-lib": "https://cdn.jsdelivr.net/npm//vega-lib?noext",
      "vega-lite": "https://cdn.jsdelivr.net/npm//vega-lite@4.0.0?noext",
      "vega-embed": "https://cdn.jsdelivr.net/npm//vega-embed@6?noext",
    };

    function loadScript(lib) {
      return new Promise(function(resolve, reject) {
        var s = document.createElement('script');
        s.src = paths[lib];
        s.async = true;
        s.onload = () => resolve(paths[lib]);
        s.onerror = () => reject(`Error loading script: ${paths[lib]}`);
        document.getElementsByTagName("head")[0].appendChild(s);
      });
    }

    function showError(err) {
      outputDiv.innerHTML = `<div class="error" style="color:red;">${err}</div>`;
      throw err;
    }

    function displayChart(vegaEmbed) {
      vegaEmbed(outputDiv, spec, embedOpt)
        .catch(err => showError(`Javascript Error: ${err.message}<br>This usually means there's a typo in your chart specification. See the javascript console for the full traceback.`));
    }

    if(typeof define === "function" && define.amd) {
      requirejs.config({paths});
      require(["vega-embed"], displayChart, err => showError(`Error loading script: ${err.message}`));
    } else if (typeof vegaEmbed === "function") {
      displayChart(vegaEmbed);
    } else {
      loadScript("vega")
        .then(() => loadScript("vega-lite"))
        .then(() => loadScript("vega-embed"))
        .catch(showError)
        .then(() => displayChart(vegaEmbed));
    }
  })({"config": {"view": {"continuousWidth": 400, "continuousHeight": 300}}, "data": {"name": "data-f02450ab61490a1363517a0190416235"}, "mark": "point", "encoding": {"color": {"type": "nominal", "field": "Origin"}, "x": {"type": "quantitative", "field": "Horsepower"}, "y": {"type": "quantitative", "field": "Miles_per_Gallon"}}, "selection": {"selector001": {"type": "interval", "bind": "scales", "encodings": ["x", "y"]}}, "$schema": "https://vega.github.io/schema/vega-lite/v4.0.0.json", "datasets": {"data-f02450ab61490a1363517a0190416235": [{"Name": "chevrolet chevelle malibu", "Miles_per_Gallon": 18.0, "Cylinders": 8, "Displacement": 307.0, "Horsepower": 130.0, "Weight_in_lbs": 3504, "Acceleration": 12.0, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "buick skylark 320", "Miles_per_Gallon": 15.0, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 165.0, "Weight_in_lbs": 3693, "Acceleration": 11.5, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth satellite", "Miles_per_Gallon": 18.0, "Cylinders": 8, "Displacement": 318.0, "Horsepower": 150.0, "Weight_in_lbs": 3436, "Acceleration": 11.0, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc rebel sst", "Miles_per_Gallon": 16.0, "Cylinders": 8, "Displacement": 304.0, "Horsepower": 150.0, "Weight_in_lbs": 3433, "Acceleration": 12.0, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford torino", "Miles_per_Gallon": 17.0, "Cylinders": 8, "Displacement": 302.0, "Horsepower": 140.0, "Weight_in_lbs": 3449, "Acceleration": 10.5, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford galaxie 500", "Miles_per_Gallon": 15.0, "Cylinders": 8, "Displacement": 429.0, "Horsepower": 198.0, "Weight_in_lbs": 4341, "Acceleration": 10.0, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet impala", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 454.0, "Horsepower": 220.0, "Weight_in_lbs": 4354, "Acceleration": 9.0, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth fury iii", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 440.0, "Horsepower": 215.0, "Weight_in_lbs": 4312, "Acceleration": 8.5, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "pontiac catalina", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 455.0, "Horsepower": 225.0, "Weight_in_lbs": 4425, "Acceleration": 10.0, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc ambassador dpl", "Miles_per_Gallon": 15.0, "Cylinders": 8, "Displacement": 390.0, "Horsepower": 190.0, "Weight_in_lbs": 3850, "Acceleration": 8.5, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "citroen ds-21 pallas", "Miles_per_Gallon": null, "Cylinders": 4, "Displacement": 133.0, "Horsepower": 115.0, "Weight_in_lbs": 3090, "Acceleration": 17.5, "Year": "1970-01-01T00:00:00", "Origin": "Europe"}, {"Name": "chevrolet chevelle concours (sw)", "Miles_per_Gallon": null, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 165.0, "Weight_in_lbs": 4142, "Acceleration": 11.5, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford torino (sw)", "Miles_per_Gallon": null, "Cylinders": 8, "Displacement": 351.0, "Horsepower": 153.0, "Weight_in_lbs": 4034, "Acceleration": 11.0, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth satellite (sw)", "Miles_per_Gallon": null, "Cylinders": 8, "Displacement": 383.0, "Horsepower": 175.0, "Weight_in_lbs": 4166, "Acceleration": 10.5, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc rebel sst (sw)", "Miles_per_Gallon": null, "Cylinders": 8, "Displacement": 360.0, "Horsepower": 175.0, "Weight_in_lbs": 3850, "Acceleration": 11.0, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge challenger se", "Miles_per_Gallon": 15.0, "Cylinders": 8, "Displacement": 383.0, "Horsepower": 170.0, "Weight_in_lbs": 3563, "Acceleration": 10.0, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth 'cuda 340", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 340.0, "Horsepower": 160.0, "Weight_in_lbs": 3609, "Acceleration": 8.0, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford mustang boss 302", "Miles_per_Gallon": null, "Cylinders": 8, "Displacement": 302.0, "Horsepower": 140.0, "Weight_in_lbs": 3353, "Acceleration": 8.0, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet monte carlo", "Miles_per_Gallon": 15.0, "Cylinders": 8, "Displacement": 400.0, "Horsepower": 150.0, "Weight_in_lbs": 3761, "Acceleration": 9.5, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "buick estate wagon (sw)", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 455.0, "Horsepower": 225.0, "Weight_in_lbs": 3086, "Acceleration": 10.0, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "toyota corona mark ii", "Miles_per_Gallon": 24.0, "Cylinders": 4, "Displacement": 113.0, "Horsepower": 95.0, "Weight_in_lbs": 2372, "Acceleration": 15.0, "Year": "1970-01-01T00:00:00", "Origin": "Japan"}, {"Name": "plymouth duster", "Miles_per_Gallon": 22.0, "Cylinders": 6, "Displacement": 198.0, "Horsepower": 95.0, "Weight_in_lbs": 2833, "Acceleration": 15.5, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc hornet", "Miles_per_Gallon": 18.0, "Cylinders": 6, "Displacement": 199.0, "Horsepower": 97.0, "Weight_in_lbs": 2774, "Acceleration": 15.5, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford maverick", "Miles_per_Gallon": 21.0, "Cylinders": 6, "Displacement": 200.0, "Horsepower": 85.0, "Weight_in_lbs": 2587, "Acceleration": 16.0, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "datsun pl510", "Miles_per_Gallon": 27.0, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 88.0, "Weight_in_lbs": 2130, "Acceleration": 14.5, "Year": "1970-01-01T00:00:00", "Origin": "Japan"}, {"Name": "volkswagen 1131 deluxe sedan", "Miles_per_Gallon": 26.0, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 46.0, "Weight_in_lbs": 1835, "Acceleration": 20.5, "Year": "1970-01-01T00:00:00", "Origin": "Europe"}, {"Name": "peugeot 504", "Miles_per_Gallon": 25.0, "Cylinders": 4, "Displacement": 110.0, "Horsepower": 87.0, "Weight_in_lbs": 2672, "Acceleration": 17.5, "Year": "1970-01-01T00:00:00", "Origin": "Europe"}, {"Name": "audi 100 ls", "Miles_per_Gallon": 24.0, "Cylinders": 4, "Displacement": 107.0, "Horsepower": 90.0, "Weight_in_lbs": 2430, "Acceleration": 14.5, "Year": "1970-01-01T00:00:00", "Origin": "Europe"}, {"Name": "saab 99e", "Miles_per_Gallon": 25.0, "Cylinders": 4, "Displacement": 104.0, "Horsepower": 95.0, "Weight_in_lbs": 2375, "Acceleration": 17.5, "Year": "1970-01-01T00:00:00", "Origin": "Europe"}, {"Name": "bmw 2002", "Miles_per_Gallon": 26.0, "Cylinders": 4, "Displacement": 121.0, "Horsepower": 113.0, "Weight_in_lbs": 2234, "Acceleration": 12.5, "Year": "1970-01-01T00:00:00", "Origin": "Europe"}, {"Name": "amc gremlin", "Miles_per_Gallon": 21.0, "Cylinders": 6, "Displacement": 199.0, "Horsepower": 90.0, "Weight_in_lbs": 2648, "Acceleration": 15.0, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford f250", "Miles_per_Gallon": 10.0, "Cylinders": 8, "Displacement": 360.0, "Horsepower": 215.0, "Weight_in_lbs": 4615, "Acceleration": 14.0, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevy c20", "Miles_per_Gallon": 10.0, "Cylinders": 8, "Displacement": 307.0, "Horsepower": 200.0, "Weight_in_lbs": 4376, "Acceleration": 15.0, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge d200", "Miles_per_Gallon": 11.0, "Cylinders": 8, "Displacement": 318.0, "Horsepower": 210.0, "Weight_in_lbs": 4382, "Acceleration": 13.5, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "hi 1200d", "Miles_per_Gallon": 9.0, "Cylinders": 8, "Displacement": 304.0, "Horsepower": 193.0, "Weight_in_lbs": 4732, "Acceleration": 18.5, "Year": "1970-01-01T00:00:00", "Origin": "USA"}, {"Name": "datsun pl510", "Miles_per_Gallon": 27.0, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 88.0, "Weight_in_lbs": 2130, "Acceleration": 14.5, "Year": "1971-01-01T00:00:00", "Origin": "Japan"}, {"Name": "chevrolet vega 2300", "Miles_per_Gallon": 28.0, "Cylinders": 4, "Displacement": 140.0, "Horsepower": 90.0, "Weight_in_lbs": 2264, "Acceleration": 15.5, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "toyota corona", "Miles_per_Gallon": 25.0, "Cylinders": 4, "Displacement": 113.0, "Horsepower": 95.0, "Weight_in_lbs": 2228, "Acceleration": 14.0, "Year": "1971-01-01T00:00:00", "Origin": "Japan"}, {"Name": "ford pinto", "Miles_per_Gallon": 25.0, "Cylinders": 4, "Displacement": 98.0, "Horsepower": null, "Weight_in_lbs": 2046, "Acceleration": 19.0, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "volkswagen super beetle 117", "Miles_per_Gallon": null, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 48.0, "Weight_in_lbs": 1978, "Acceleration": 20.0, "Year": "1971-01-01T00:00:00", "Origin": "Europe"}, {"Name": "amc gremlin", "Miles_per_Gallon": 19.0, "Cylinders": 6, "Displacement": 232.0, "Horsepower": 100.0, "Weight_in_lbs": 2634, "Acceleration": 13.0, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth satellite custom", "Miles_per_Gallon": 16.0, "Cylinders": 6, "Displacement": 225.0, "Horsepower": 105.0, "Weight_in_lbs": 3439, "Acceleration": 15.5, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet chevelle malibu", "Miles_per_Gallon": 17.0, "Cylinders": 6, "Displacement": 250.0, "Horsepower": 100.0, "Weight_in_lbs": 3329, "Acceleration": 15.5, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford torino 500", "Miles_per_Gallon": 19.0, "Cylinders": 6, "Displacement": 250.0, "Horsepower": 88.0, "Weight_in_lbs": 3302, "Acceleration": 15.5, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc matador", "Miles_per_Gallon": 18.0, "Cylinders": 6, "Displacement": 232.0, "Horsepower": 100.0, "Weight_in_lbs": 3288, "Acceleration": 15.5, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet impala", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 165.0, "Weight_in_lbs": 4209, "Acceleration": 12.0, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "pontiac catalina brougham", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 400.0, "Horsepower": 175.0, "Weight_in_lbs": 4464, "Acceleration": 11.5, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford galaxie 500", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 351.0, "Horsepower": 153.0, "Weight_in_lbs": 4154, "Acceleration": 13.5, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth fury iii", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 318.0, "Horsepower": 150.0, "Weight_in_lbs": 4096, "Acceleration": 13.0, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge monaco (sw)", "Miles_per_Gallon": 12.0, "Cylinders": 8, "Displacement": 383.0, "Horsepower": 180.0, "Weight_in_lbs": 4955, "Acceleration": 11.5, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford country squire (sw)", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 400.0, "Horsepower": 170.0, "Weight_in_lbs": 4746, "Acceleration": 12.0, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "pontiac safari (sw)", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 400.0, "Horsepower": 175.0, "Weight_in_lbs": 5140, "Acceleration": 12.0, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc hornet sportabout (sw)", "Miles_per_Gallon": 18.0, "Cylinders": 6, "Displacement": 258.0, "Horsepower": 110.0, "Weight_in_lbs": 2962, "Acceleration": 13.5, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet vega (sw)", "Miles_per_Gallon": 22.0, "Cylinders": 4, "Displacement": 140.0, "Horsepower": 72.0, "Weight_in_lbs": 2408, "Acceleration": 19.0, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "pontiac firebird", "Miles_per_Gallon": 19.0, "Cylinders": 6, "Displacement": 250.0, "Horsepower": 100.0, "Weight_in_lbs": 3282, "Acceleration": 15.0, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford mustang", "Miles_per_Gallon": 18.0, "Cylinders": 6, "Displacement": 250.0, "Horsepower": 88.0, "Weight_in_lbs": 3139, "Acceleration": 14.5, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "mercury capri 2000", "Miles_per_Gallon": 23.0, "Cylinders": 4, "Displacement": 122.0, "Horsepower": 86.0, "Weight_in_lbs": 2220, "Acceleration": 14.0, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "opel 1900", "Miles_per_Gallon": 28.0, "Cylinders": 4, "Displacement": 116.0, "Horsepower": 90.0, "Weight_in_lbs": 2123, "Acceleration": 14.0, "Year": "1971-01-01T00:00:00", "Origin": "Europe"}, {"Name": "peugeot 304", "Miles_per_Gallon": 30.0, "Cylinders": 4, "Displacement": 79.0, "Horsepower": 70.0, "Weight_in_lbs": 2074, "Acceleration": 19.5, "Year": "1971-01-01T00:00:00", "Origin": "Europe"}, {"Name": "fiat 124b", "Miles_per_Gallon": 30.0, "Cylinders": 4, "Displacement": 88.0, "Horsepower": 76.0, "Weight_in_lbs": 2065, "Acceleration": 14.5, "Year": "1971-01-01T00:00:00", "Origin": "Europe"}, {"Name": "toyota corolla 1200", "Miles_per_Gallon": 31.0, "Cylinders": 4, "Displacement": 71.0, "Horsepower": 65.0, "Weight_in_lbs": 1773, "Acceleration": 19.0, "Year": "1971-01-01T00:00:00", "Origin": "Japan"}, {"Name": "datsun 1200", "Miles_per_Gallon": 35.0, "Cylinders": 4, "Displacement": 72.0, "Horsepower": 69.0, "Weight_in_lbs": 1613, "Acceleration": 18.0, "Year": "1971-01-01T00:00:00", "Origin": "Japan"}, {"Name": "volkswagen model 111", "Miles_per_Gallon": 27.0, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 60.0, "Weight_in_lbs": 1834, "Acceleration": 19.0, "Year": "1971-01-01T00:00:00", "Origin": "Europe"}, {"Name": "plymouth cricket", "Miles_per_Gallon": 26.0, "Cylinders": 4, "Displacement": 91.0, "Horsepower": 70.0, "Weight_in_lbs": 1955, "Acceleration": 20.5, "Year": "1971-01-01T00:00:00", "Origin": "USA"}, {"Name": "toyota corona hardtop", "Miles_per_Gallon": 24.0, "Cylinders": 4, "Displacement": 113.0, "Horsepower": 95.0, "Weight_in_lbs": 2278, "Acceleration": 15.5, "Year": "1972-01-01T00:00:00", "Origin": "Japan"}, {"Name": "dodge colt hardtop", "Miles_per_Gallon": 25.0, "Cylinders": 4, "Displacement": 97.5, "Horsepower": 80.0, "Weight_in_lbs": 2126, "Acceleration": 17.0, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "volkswagen type 3", "Miles_per_Gallon": 23.0, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 54.0, "Weight_in_lbs": 2254, "Acceleration": 23.5, "Year": "1972-01-01T00:00:00", "Origin": "Europe"}, {"Name": "chevrolet vega", "Miles_per_Gallon": 20.0, "Cylinders": 4, "Displacement": 140.0, "Horsepower": 90.0, "Weight_in_lbs": 2408, "Acceleration": 19.5, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford pinto runabout", "Miles_per_Gallon": 21.0, "Cylinders": 4, "Displacement": 122.0, "Horsepower": 86.0, "Weight_in_lbs": 2226, "Acceleration": 16.5, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet impala", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 165.0, "Weight_in_lbs": 4274, "Acceleration": 12.0, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "pontiac catalina", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 400.0, "Horsepower": 175.0, "Weight_in_lbs": 4385, "Acceleration": 12.0, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth fury iii", "Miles_per_Gallon": 15.0, "Cylinders": 8, "Displacement": 318.0, "Horsepower": 150.0, "Weight_in_lbs": 4135, "Acceleration": 13.5, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford galaxie 500", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 351.0, "Horsepower": 153.0, "Weight_in_lbs": 4129, "Acceleration": 13.0, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc ambassador sst", "Miles_per_Gallon": 17.0, "Cylinders": 8, "Displacement": 304.0, "Horsepower": 150.0, "Weight_in_lbs": 3672, "Acceleration": 11.5, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "mercury marquis", "Miles_per_Gallon": 11.0, "Cylinders": 8, "Displacement": 429.0, "Horsepower": 208.0, "Weight_in_lbs": 4633, "Acceleration": 11.0, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "buick lesabre custom", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 155.0, "Weight_in_lbs": 4502, "Acceleration": 13.5, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "oldsmobile delta 88 royale", "Miles_per_Gallon": 12.0, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 160.0, "Weight_in_lbs": 4456, "Acceleration": 13.5, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "chrysler newport royal", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 400.0, "Horsepower": 190.0, "Weight_in_lbs": 4422, "Acceleration": 12.5, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "mazda rx2 coupe", "Miles_per_Gallon": 19.0, "Cylinders": 3, "Displacement": 70.0, "Horsepower": 97.0, "Weight_in_lbs": 2330, "Acceleration": 13.5, "Year": "1972-01-01T00:00:00", "Origin": "Japan"}, {"Name": "amc matador (sw)", "Miles_per_Gallon": 15.0, "Cylinders": 8, "Displacement": 304.0, "Horsepower": 150.0, "Weight_in_lbs": 3892, "Acceleration": 12.5, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet chevelle concours (sw)", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 307.0, "Horsepower": 130.0, "Weight_in_lbs": 4098, "Acceleration": 14.0, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford gran torino (sw)", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 302.0, "Horsepower": 140.0, "Weight_in_lbs": 4294, "Acceleration": 16.0, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth satellite custom (sw)", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 318.0, "Horsepower": 150.0, "Weight_in_lbs": 4077, "Acceleration": 14.0, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "volvo 145e (sw)", "Miles_per_Gallon": 18.0, "Cylinders": 4, "Displacement": 121.0, "Horsepower": 112.0, "Weight_in_lbs": 2933, "Acceleration": 14.5, "Year": "1972-01-01T00:00:00", "Origin": "Europe"}, {"Name": "volkswagen 411 (sw)", "Miles_per_Gallon": 22.0, "Cylinders": 4, "Displacement": 121.0, "Horsepower": 76.0, "Weight_in_lbs": 2511, "Acceleration": 18.0, "Year": "1972-01-01T00:00:00", "Origin": "Europe"}, {"Name": "peugeot 504 (sw)", "Miles_per_Gallon": 21.0, "Cylinders": 4, "Displacement": 120.0, "Horsepower": 87.0, "Weight_in_lbs": 2979, "Acceleration": 19.5, "Year": "1972-01-01T00:00:00", "Origin": "Europe"}, {"Name": "renault 12 (sw)", "Miles_per_Gallon": 26.0, "Cylinders": 4, "Displacement": 96.0, "Horsepower": 69.0, "Weight_in_lbs": 2189, "Acceleration": 18.0, "Year": "1972-01-01T00:00:00", "Origin": "Europe"}, {"Name": "ford pinto (sw)", "Miles_per_Gallon": 22.0, "Cylinders": 4, "Displacement": 122.0, "Horsepower": 86.0, "Weight_in_lbs": 2395, "Acceleration": 16.0, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "datsun 510 (sw)", "Miles_per_Gallon": 28.0, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 92.0, "Weight_in_lbs": 2288, "Acceleration": 17.0, "Year": "1972-01-01T00:00:00", "Origin": "Japan"}, {"Name": "toyouta corona mark ii (sw)", "Miles_per_Gallon": 23.0, "Cylinders": 4, "Displacement": 120.0, "Horsepower": 97.0, "Weight_in_lbs": 2506, "Acceleration": 14.5, "Year": "1972-01-01T00:00:00", "Origin": "Japan"}, {"Name": "dodge colt (sw)", "Miles_per_Gallon": 28.0, "Cylinders": 4, "Displacement": 98.0, "Horsepower": 80.0, "Weight_in_lbs": 2164, "Acceleration": 15.0, "Year": "1972-01-01T00:00:00", "Origin": "USA"}, {"Name": "toyota corolla 1600 (sw)", "Miles_per_Gallon": 27.0, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 88.0, "Weight_in_lbs": 2100, "Acceleration": 16.5, "Year": "1972-01-01T00:00:00", "Origin": "Japan"}, {"Name": "buick century 350", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 175.0, "Weight_in_lbs": 4100, "Acceleration": 13.0, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc matador", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 304.0, "Horsepower": 150.0, "Weight_in_lbs": 3672, "Acceleration": 11.5, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet malibu", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 145.0, "Weight_in_lbs": 3988, "Acceleration": 13.0, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford gran torino", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 302.0, "Horsepower": 137.0, "Weight_in_lbs": 4042, "Acceleration": 14.5, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge coronet custom", "Miles_per_Gallon": 15.0, "Cylinders": 8, "Displacement": 318.0, "Horsepower": 150.0, "Weight_in_lbs": 3777, "Acceleration": 12.5, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "mercury marquis brougham", "Miles_per_Gallon": 12.0, "Cylinders": 8, "Displacement": 429.0, "Horsepower": 198.0, "Weight_in_lbs": 4952, "Acceleration": 11.5, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet caprice classic", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 400.0, "Horsepower": 150.0, "Weight_in_lbs": 4464, "Acceleration": 12.0, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford ltd", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 351.0, "Horsepower": 158.0, "Weight_in_lbs": 4363, "Acceleration": 13.0, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth fury gran sedan", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 318.0, "Horsepower": 150.0, "Weight_in_lbs": 4237, "Acceleration": 14.5, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "chrysler new yorker brougham", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 440.0, "Horsepower": 215.0, "Weight_in_lbs": 4735, "Acceleration": 11.0, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "buick electra 225 custom", "Miles_per_Gallon": 12.0, "Cylinders": 8, "Displacement": 455.0, "Horsepower": 225.0, "Weight_in_lbs": 4951, "Acceleration": 11.0, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc ambassador brougham", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 360.0, "Horsepower": 175.0, "Weight_in_lbs": 3821, "Acceleration": 11.0, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth valiant", "Miles_per_Gallon": 18.0, "Cylinders": 6, "Displacement": 225.0, "Horsepower": 105.0, "Weight_in_lbs": 3121, "Acceleration": 16.5, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet nova custom", "Miles_per_Gallon": 16.0, "Cylinders": 6, "Displacement": 250.0, "Horsepower": 100.0, "Weight_in_lbs": 3278, "Acceleration": 18.0, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc hornet", "Miles_per_Gallon": 18.0, "Cylinders": 6, "Displacement": 232.0, "Horsepower": 100.0, "Weight_in_lbs": 2945, "Acceleration": 16.0, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford maverick", "Miles_per_Gallon": 18.0, "Cylinders": 6, "Displacement": 250.0, "Horsepower": 88.0, "Weight_in_lbs": 3021, "Acceleration": 16.5, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth duster", "Miles_per_Gallon": 23.0, "Cylinders": 6, "Displacement": 198.0, "Horsepower": 95.0, "Weight_in_lbs": 2904, "Acceleration": 16.0, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "volkswagen super beetle", "Miles_per_Gallon": 26.0, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 46.0, "Weight_in_lbs": 1950, "Acceleration": 21.0, "Year": "1973-01-01T00:00:00", "Origin": "Europe"}, {"Name": "chevrolet impala", "Miles_per_Gallon": 11.0, "Cylinders": 8, "Displacement": 400.0, "Horsepower": 150.0, "Weight_in_lbs": 4997, "Acceleration": 14.0, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford country", "Miles_per_Gallon": 12.0, "Cylinders": 8, "Displacement": 400.0, "Horsepower": 167.0, "Weight_in_lbs": 4906, "Acceleration": 12.5, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth custom suburb", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 360.0, "Horsepower": 170.0, "Weight_in_lbs": 4654, "Acceleration": 13.0, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "oldsmobile vista cruiser", "Miles_per_Gallon": 12.0, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 180.0, "Weight_in_lbs": 4499, "Acceleration": 12.5, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc gremlin", "Miles_per_Gallon": 18.0, "Cylinders": 6, "Displacement": 232.0, "Horsepower": 100.0, "Weight_in_lbs": 2789, "Acceleration": 15.0, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "toyota carina", "Miles_per_Gallon": 20.0, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 88.0, "Weight_in_lbs": 2279, "Acceleration": 19.0, "Year": "1973-01-01T00:00:00", "Origin": "Japan"}, {"Name": "chevrolet vega", "Miles_per_Gallon": 21.0, "Cylinders": 4, "Displacement": 140.0, "Horsepower": 72.0, "Weight_in_lbs": 2401, "Acceleration": 19.5, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "datsun 610", "Miles_per_Gallon": 22.0, "Cylinders": 4, "Displacement": 108.0, "Horsepower": 94.0, "Weight_in_lbs": 2379, "Acceleration": 16.5, "Year": "1973-01-01T00:00:00", "Origin": "Japan"}, {"Name": "maxda rx3", "Miles_per_Gallon": 18.0, "Cylinders": 3, "Displacement": 70.0, "Horsepower": 90.0, "Weight_in_lbs": 2124, "Acceleration": 13.5, "Year": "1973-01-01T00:00:00", "Origin": "Japan"}, {"Name": "ford pinto", "Miles_per_Gallon": 19.0, "Cylinders": 4, "Displacement": 122.0, "Horsepower": 85.0, "Weight_in_lbs": 2310, "Acceleration": 18.5, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "mercury capri v6", "Miles_per_Gallon": 21.0, "Cylinders": 6, "Displacement": 155.0, "Horsepower": 107.0, "Weight_in_lbs": 2472, "Acceleration": 14.0, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "fiat 124 sport coupe", "Miles_per_Gallon": 26.0, "Cylinders": 4, "Displacement": 98.0, "Horsepower": 90.0, "Weight_in_lbs": 2265, "Acceleration": 15.5, "Year": "1973-01-01T00:00:00", "Origin": "Europe"}, {"Name": "chevrolet monte carlo s", "Miles_per_Gallon": 15.0, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 145.0, "Weight_in_lbs": 4082, "Acceleration": 13.0, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "pontiac grand prix", "Miles_per_Gallon": 16.0, "Cylinders": 8, "Displacement": 400.0, "Horsepower": 230.0, "Weight_in_lbs": 4278, "Acceleration": 9.5, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "fiat 128", "Miles_per_Gallon": 29.0, "Cylinders": 4, "Displacement": 68.0, "Horsepower": 49.0, "Weight_in_lbs": 1867, "Acceleration": 19.5, "Year": "1973-01-01T00:00:00", "Origin": "Europe"}, {"Name": "opel manta", "Miles_per_Gallon": 24.0, "Cylinders": 4, "Displacement": 116.0, "Horsepower": 75.0, "Weight_in_lbs": 2158, "Acceleration": 15.5, "Year": "1973-01-01T00:00:00", "Origin": "Europe"}, {"Name": "audi 100ls", "Miles_per_Gallon": 20.0, "Cylinders": 4, "Displacement": 114.0, "Horsepower": 91.0, "Weight_in_lbs": 2582, "Acceleration": 14.0, "Year": "1973-01-01T00:00:00", "Origin": "Europe"}, {"Name": "volvo 144ea", "Miles_per_Gallon": 19.0, "Cylinders": 4, "Displacement": 121.0, "Horsepower": 112.0, "Weight_in_lbs": 2868, "Acceleration": 15.5, "Year": "1973-01-01T00:00:00", "Origin": "Europe"}, {"Name": "dodge dart custom", "Miles_per_Gallon": 15.0, "Cylinders": 8, "Displacement": 318.0, "Horsepower": 150.0, "Weight_in_lbs": 3399, "Acceleration": 11.0, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "saab 99le", "Miles_per_Gallon": 24.0, "Cylinders": 4, "Displacement": 121.0, "Horsepower": 110.0, "Weight_in_lbs": 2660, "Acceleration": 14.0, "Year": "1973-01-01T00:00:00", "Origin": "Europe"}, {"Name": "toyota mark ii", "Miles_per_Gallon": 20.0, "Cylinders": 6, "Displacement": 156.0, "Horsepower": 122.0, "Weight_in_lbs": 2807, "Acceleration": 13.5, "Year": "1973-01-01T00:00:00", "Origin": "Japan"}, {"Name": "oldsmobile omega", "Miles_per_Gallon": 11.0, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 180.0, "Weight_in_lbs": 3664, "Acceleration": 11.0, "Year": "1973-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth duster", "Miles_per_Gallon": 20.0, "Cylinders": 6, "Displacement": 198.0, "Horsepower": 95.0, "Weight_in_lbs": 3102, "Acceleration": 16.5, "Year": "1974-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford maverick", "Miles_per_Gallon": 21.0, "Cylinders": 6, "Displacement": 200.0, "Horsepower": null, "Weight_in_lbs": 2875, "Acceleration": 17.0, "Year": "1974-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc hornet", "Miles_per_Gallon": 19.0, "Cylinders": 6, "Displacement": 232.0, "Horsepower": 100.0, "Weight_in_lbs": 2901, "Acceleration": 16.0, "Year": "1974-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet nova", "Miles_per_Gallon": 15.0, "Cylinders": 6, "Displacement": 250.0, "Horsepower": 100.0, "Weight_in_lbs": 3336, "Acceleration": 17.0, "Year": "1974-01-01T00:00:00", "Origin": "USA"}, {"Name": "datsun b210", "Miles_per_Gallon": 31.0, "Cylinders": 4, "Displacement": 79.0, "Horsepower": 67.0, "Weight_in_lbs": 1950, "Acceleration": 19.0, "Year": "1974-01-01T00:00:00", "Origin": "Japan"}, {"Name": "ford pinto", "Miles_per_Gallon": 26.0, "Cylinders": 4, "Displacement": 122.0, "Horsepower": 80.0, "Weight_in_lbs": 2451, "Acceleration": 16.5, "Year": "1974-01-01T00:00:00", "Origin": "USA"}, {"Name": "toyota corolla 1200", "Miles_per_Gallon": 32.0, "Cylinders": 4, "Displacement": 71.0, "Horsepower": 65.0, "Weight_in_lbs": 1836, "Acceleration": 21.0, "Year": "1974-01-01T00:00:00", "Origin": "Japan"}, {"Name": "chevrolet vega", "Miles_per_Gallon": 25.0, "Cylinders": 4, "Displacement": 140.0, "Horsepower": 75.0, "Weight_in_lbs": 2542, "Acceleration": 17.0, "Year": "1974-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet chevelle malibu classic", "Miles_per_Gallon": 16.0, "Cylinders": 6, "Displacement": 250.0, "Horsepower": 100.0, "Weight_in_lbs": 3781, "Acceleration": 17.0, "Year": "1974-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc matador", "Miles_per_Gallon": 16.0, "Cylinders": 6, "Displacement": 258.0, "Horsepower": 110.0, "Weight_in_lbs": 3632, "Acceleration": 18.0, "Year": "1974-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth satellite sebring", "Miles_per_Gallon": 18.0, "Cylinders": 6, "Displacement": 225.0, "Horsepower": 105.0, "Weight_in_lbs": 3613, "Acceleration": 16.5, "Year": "1974-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford gran torino", "Miles_per_Gallon": 16.0, "Cylinders": 8, "Displacement": 302.0, "Horsepower": 140.0, "Weight_in_lbs": 4141, "Acceleration": 14.0, "Year": "1974-01-01T00:00:00", "Origin": "USA"}, {"Name": "buick century luxus (sw)", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 150.0, "Weight_in_lbs": 4699, "Acceleration": 14.5, "Year": "1974-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge coronet custom (sw)", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 318.0, "Horsepower": 150.0, "Weight_in_lbs": 4457, "Acceleration": 13.5, "Year": "1974-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford gran torino (sw)", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 302.0, "Horsepower": 140.0, "Weight_in_lbs": 4638, "Acceleration": 16.0, "Year": "1974-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc matador (sw)", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 304.0, "Horsepower": 150.0, "Weight_in_lbs": 4257, "Acceleration": 15.5, "Year": "1974-01-01T00:00:00", "Origin": "USA"}, {"Name": "audi fox", "Miles_per_Gallon": 29.0, "Cylinders": 4, "Displacement": 98.0, "Horsepower": 83.0, "Weight_in_lbs": 2219, "Acceleration": 16.5, "Year": "1974-01-01T00:00:00", "Origin": "Europe"}, {"Name": "volkswagen dasher", "Miles_per_Gallon": 26.0, "Cylinders": 4, "Displacement": 79.0, "Horsepower": 67.0, "Weight_in_lbs": 1963, "Acceleration": 15.5, "Year": "1974-01-01T00:00:00", "Origin": "Europe"}, {"Name": "opel manta", "Miles_per_Gallon": 26.0, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 78.0, "Weight_in_lbs": 2300, "Acceleration": 14.5, "Year": "1974-01-01T00:00:00", "Origin": "Europe"}, {"Name": "toyota corona", "Miles_per_Gallon": 31.0, "Cylinders": 4, "Displacement": 76.0, "Horsepower": 52.0, "Weight_in_lbs": 1649, "Acceleration": 16.5, "Year": "1974-01-01T00:00:00", "Origin": "Japan"}, {"Name": "datsun 710", "Miles_per_Gallon": 32.0, "Cylinders": 4, "Displacement": 83.0, "Horsepower": 61.0, "Weight_in_lbs": 2003, "Acceleration": 19.0, "Year": "1974-01-01T00:00:00", "Origin": "Japan"}, {"Name": "dodge colt", "Miles_per_Gallon": 28.0, "Cylinders": 4, "Displacement": 90.0, "Horsepower": 75.0, "Weight_in_lbs": 2125, "Acceleration": 14.5, "Year": "1974-01-01T00:00:00", "Origin": "USA"}, {"Name": "fiat 128", "Miles_per_Gallon": 24.0, "Cylinders": 4, "Displacement": 90.0, "Horsepower": 75.0, "Weight_in_lbs": 2108, "Acceleration": 15.5, "Year": "1974-01-01T00:00:00", "Origin": "Europe"}, {"Name": "fiat 124 tc", "Miles_per_Gallon": 26.0, "Cylinders": 4, "Displacement": 116.0, "Horsepower": 75.0, "Weight_in_lbs": 2246, "Acceleration": 14.0, "Year": "1974-01-01T00:00:00", "Origin": "Europe"}, {"Name": "honda civic", "Miles_per_Gallon": 24.0, "Cylinders": 4, "Displacement": 120.0, "Horsepower": 97.0, "Weight_in_lbs": 2489, "Acceleration": 15.0, "Year": "1974-01-01T00:00:00", "Origin": "Japan"}, {"Name": "subaru", "Miles_per_Gallon": 26.0, "Cylinders": 4, "Displacement": 108.0, "Horsepower": 93.0, "Weight_in_lbs": 2391, "Acceleration": 15.5, "Year": "1974-01-01T00:00:00", "Origin": "Japan"}, {"Name": "fiat x1.9", "Miles_per_Gallon": 31.0, "Cylinders": 4, "Displacement": 79.0, "Horsepower": 67.0, "Weight_in_lbs": 2000, "Acceleration": 16.0, "Year": "1974-01-01T00:00:00", "Origin": "Europe"}, {"Name": "plymouth valiant custom", "Miles_per_Gallon": 19.0, "Cylinders": 6, "Displacement": 225.0, "Horsepower": 95.0, "Weight_in_lbs": 3264, "Acceleration": 16.0, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet nova", "Miles_per_Gallon": 18.0, "Cylinders": 6, "Displacement": 250.0, "Horsepower": 105.0, "Weight_in_lbs": 3459, "Acceleration": 16.0, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "mercury monarch", "Miles_per_Gallon": 15.0, "Cylinders": 6, "Displacement": 250.0, "Horsepower": 72.0, "Weight_in_lbs": 3432, "Acceleration": 21.0, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford maverick", "Miles_per_Gallon": 15.0, "Cylinders": 6, "Displacement": 250.0, "Horsepower": 72.0, "Weight_in_lbs": 3158, "Acceleration": 19.5, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "pontiac catalina", "Miles_per_Gallon": 16.0, "Cylinders": 8, "Displacement": 400.0, "Horsepower": 170.0, "Weight_in_lbs": 4668, "Acceleration": 11.5, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet bel air", "Miles_per_Gallon": 15.0, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 145.0, "Weight_in_lbs": 4440, "Acceleration": 14.0, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth grand fury", "Miles_per_Gallon": 16.0, "Cylinders": 8, "Displacement": 318.0, "Horsepower": 150.0, "Weight_in_lbs": 4498, "Acceleration": 14.5, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford ltd", "Miles_per_Gallon": 14.0, "Cylinders": 8, "Displacement": 351.0, "Horsepower": 148.0, "Weight_in_lbs": 4657, "Acceleration": 13.5, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "buick century", "Miles_per_Gallon": 17.0, "Cylinders": 6, "Displacement": 231.0, "Horsepower": 110.0, "Weight_in_lbs": 3907, "Acceleration": 21.0, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevroelt chevelle malibu", "Miles_per_Gallon": 16.0, "Cylinders": 6, "Displacement": 250.0, "Horsepower": 105.0, "Weight_in_lbs": 3897, "Acceleration": 18.5, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc matador", "Miles_per_Gallon": 15.0, "Cylinders": 6, "Displacement": 258.0, "Horsepower": 110.0, "Weight_in_lbs": 3730, "Acceleration": 19.0, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth fury", "Miles_per_Gallon": 18.0, "Cylinders": 6, "Displacement": 225.0, "Horsepower": 95.0, "Weight_in_lbs": 3785, "Acceleration": 19.0, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "buick skyhawk", "Miles_per_Gallon": 21.0, "Cylinders": 6, "Displacement": 231.0, "Horsepower": 110.0, "Weight_in_lbs": 3039, "Acceleration": 15.0, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet monza 2+2", "Miles_per_Gallon": 20.0, "Cylinders": 8, "Displacement": 262.0, "Horsepower": 110.0, "Weight_in_lbs": 3221, "Acceleration": 13.5, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford mustang ii", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 302.0, "Horsepower": 129.0, "Weight_in_lbs": 3169, "Acceleration": 12.0, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "toyota corolla", "Miles_per_Gallon": 29.0, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 75.0, "Weight_in_lbs": 2171, "Acceleration": 16.0, "Year": "1975-01-01T00:00:00", "Origin": "Japan"}, {"Name": "ford pinto", "Miles_per_Gallon": 23.0, "Cylinders": 4, "Displacement": 140.0, "Horsepower": 83.0, "Weight_in_lbs": 2639, "Acceleration": 17.0, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc gremlin", "Miles_per_Gallon": 20.0, "Cylinders": 6, "Displacement": 232.0, "Horsepower": 100.0, "Weight_in_lbs": 2914, "Acceleration": 16.0, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "pontiac astro", "Miles_per_Gallon": 23.0, "Cylinders": 4, "Displacement": 140.0, "Horsepower": 78.0, "Weight_in_lbs": 2592, "Acceleration": 18.5, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "toyota corona", "Miles_per_Gallon": 24.0, "Cylinders": 4, "Displacement": 134.0, "Horsepower": 96.0, "Weight_in_lbs": 2702, "Acceleration": 13.5, "Year": "1975-01-01T00:00:00", "Origin": "Japan"}, {"Name": "volkswagen dasher", "Miles_per_Gallon": 25.0, "Cylinders": 4, "Displacement": 90.0, "Horsepower": 71.0, "Weight_in_lbs": 2223, "Acceleration": 16.5, "Year": "1975-01-01T00:00:00", "Origin": "Europe"}, {"Name": "datsun 710", "Miles_per_Gallon": 24.0, "Cylinders": 4, "Displacement": 119.0, "Horsepower": 97.0, "Weight_in_lbs": 2545, "Acceleration": 17.0, "Year": "1975-01-01T00:00:00", "Origin": "Japan"}, {"Name": "ford pinto", "Miles_per_Gallon": 18.0, "Cylinders": 6, "Displacement": 171.0, "Horsepower": 97.0, "Weight_in_lbs": 2984, "Acceleration": 14.5, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "volkswagen rabbit", "Miles_per_Gallon": 29.0, "Cylinders": 4, "Displacement": 90.0, "Horsepower": 70.0, "Weight_in_lbs": 1937, "Acceleration": 14.0, "Year": "1975-01-01T00:00:00", "Origin": "Europe"}, {"Name": "amc pacer", "Miles_per_Gallon": 19.0, "Cylinders": 6, "Displacement": 232.0, "Horsepower": 90.0, "Weight_in_lbs": 3211, "Acceleration": 17.0, "Year": "1975-01-01T00:00:00", "Origin": "USA"}, {"Name": "audi 100ls", "Miles_per_Gallon": 23.0, "Cylinders": 4, "Displacement": 115.0, "Horsepower": 95.0, "Weight_in_lbs": 2694, "Acceleration": 15.0, "Year": "1975-01-01T00:00:00", "Origin": "Europe"}, {"Name": "peugeot 504", "Miles_per_Gallon": 23.0, "Cylinders": 4, "Displacement": 120.0, "Horsepower": 88.0, "Weight_in_lbs": 2957, "Acceleration": 17.0, "Year": "1975-01-01T00:00:00", "Origin": "Europe"}, {"Name": "volvo 244dl", "Miles_per_Gallon": 22.0, "Cylinders": 4, "Displacement": 121.0, "Horsepower": 98.0, "Weight_in_lbs": 2945, "Acceleration": 14.5, "Year": "1975-01-01T00:00:00", "Origin": "Europe"}, {"Name": "saab 99le", "Miles_per_Gallon": 25.0, "Cylinders": 4, "Displacement": 121.0, "Horsepower": 115.0, "Weight_in_lbs": 2671, "Acceleration": 13.5, "Year": "1975-01-01T00:00:00", "Origin": "Europe"}, {"Name": "honda civic cvcc", "Miles_per_Gallon": 33.0, "Cylinders": 4, "Displacement": 91.0, "Horsepower": 53.0, "Weight_in_lbs": 1795, "Acceleration": 17.5, "Year": "1975-01-01T00:00:00", "Origin": "Japan"}, {"Name": "fiat 131", "Miles_per_Gallon": 28.0, "Cylinders": 4, "Displacement": 107.0, "Horsepower": 86.0, "Weight_in_lbs": 2464, "Acceleration": 15.5, "Year": "1976-01-01T00:00:00", "Origin": "Europe"}, {"Name": "opel 1900", "Miles_per_Gallon": 25.0, "Cylinders": 4, "Displacement": 116.0, "Horsepower": 81.0, "Weight_in_lbs": 2220, "Acceleration": 16.9, "Year": "1976-01-01T00:00:00", "Origin": "Europe"}, {"Name": "capri ii", "Miles_per_Gallon": 25.0, "Cylinders": 4, "Displacement": 140.0, "Horsepower": 92.0, "Weight_in_lbs": 2572, "Acceleration": 14.9, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge colt", "Miles_per_Gallon": 26.0, "Cylinders": 4, "Displacement": 98.0, "Horsepower": 79.0, "Weight_in_lbs": 2255, "Acceleration": 17.7, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "renault 12tl", "Miles_per_Gallon": 27.0, "Cylinders": 4, "Displacement": 101.0, "Horsepower": 83.0, "Weight_in_lbs": 2202, "Acceleration": 15.3, "Year": "1976-01-01T00:00:00", "Origin": "Europe"}, {"Name": "chevrolet chevelle malibu classic", "Miles_per_Gallon": 17.5, "Cylinders": 8, "Displacement": 305.0, "Horsepower": 140.0, "Weight_in_lbs": 4215, "Acceleration": 13.0, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge coronet brougham", "Miles_per_Gallon": 16.0, "Cylinders": 8, "Displacement": 318.0, "Horsepower": 150.0, "Weight_in_lbs": 4190, "Acceleration": 13.0, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc matador", "Miles_per_Gallon": 15.5, "Cylinders": 8, "Displacement": 304.0, "Horsepower": 120.0, "Weight_in_lbs": 3962, "Acceleration": 13.9, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford gran torino", "Miles_per_Gallon": 14.5, "Cylinders": 8, "Displacement": 351.0, "Horsepower": 152.0, "Weight_in_lbs": 4215, "Acceleration": 12.8, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth valiant", "Miles_per_Gallon": 22.0, "Cylinders": 6, "Displacement": 225.0, "Horsepower": 100.0, "Weight_in_lbs": 3233, "Acceleration": 15.4, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet nova", "Miles_per_Gallon": 22.0, "Cylinders": 6, "Displacement": 250.0, "Horsepower": 105.0, "Weight_in_lbs": 3353, "Acceleration": 14.5, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford maverick", "Miles_per_Gallon": 24.0, "Cylinders": 6, "Displacement": 200.0, "Horsepower": 81.0, "Weight_in_lbs": 3012, "Acceleration": 17.6, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc hornet", "Miles_per_Gallon": 22.5, "Cylinders": 6, "Displacement": 232.0, "Horsepower": 90.0, "Weight_in_lbs": 3085, "Acceleration": 17.6, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet chevette", "Miles_per_Gallon": 29.0, "Cylinders": 4, "Displacement": 85.0, "Horsepower": 52.0, "Weight_in_lbs": 2035, "Acceleration": 22.2, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet woody", "Miles_per_Gallon": 24.5, "Cylinders": 4, "Displacement": 98.0, "Horsepower": 60.0, "Weight_in_lbs": 2164, "Acceleration": 22.1, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "vw rabbit", "Miles_per_Gallon": 29.0, "Cylinders": 4, "Displacement": 90.0, "Horsepower": 70.0, "Weight_in_lbs": 1937, "Acceleration": 14.2, "Year": "1976-01-01T00:00:00", "Origin": "Europe"}, {"Name": "honda civic", "Miles_per_Gallon": 33.0, "Cylinders": 4, "Displacement": 91.0, "Horsepower": 53.0, "Weight_in_lbs": 1795, "Acceleration": 17.4, "Year": "1976-01-01T00:00:00", "Origin": "Japan"}, {"Name": "dodge aspen se", "Miles_per_Gallon": 20.0, "Cylinders": 6, "Displacement": 225.0, "Horsepower": 100.0, "Weight_in_lbs": 3651, "Acceleration": 17.7, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford granada ghia", "Miles_per_Gallon": 18.0, "Cylinders": 6, "Displacement": 250.0, "Horsepower": 78.0, "Weight_in_lbs": 3574, "Acceleration": 21.0, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "pontiac ventura sj", "Miles_per_Gallon": 18.5, "Cylinders": 6, "Displacement": 250.0, "Horsepower": 110.0, "Weight_in_lbs": 3645, "Acceleration": 16.2, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc pacer d/l", "Miles_per_Gallon": 17.5, "Cylinders": 6, "Displacement": 258.0, "Horsepower": 95.0, "Weight_in_lbs": 3193, "Acceleration": 17.8, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "volkswagen rabbit", "Miles_per_Gallon": 29.5, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 71.0, "Weight_in_lbs": 1825, "Acceleration": 12.2, "Year": "1976-01-01T00:00:00", "Origin": "Europe"}, {"Name": "datsun b-210", "Miles_per_Gallon": 32.0, "Cylinders": 4, "Displacement": 85.0, "Horsepower": 70.0, "Weight_in_lbs": 1990, "Acceleration": 17.0, "Year": "1976-01-01T00:00:00", "Origin": "Japan"}, {"Name": "toyota corolla", "Miles_per_Gallon": 28.0, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 75.0, "Weight_in_lbs": 2155, "Acceleration": 16.4, "Year": "1976-01-01T00:00:00", "Origin": "Japan"}, {"Name": "ford pinto", "Miles_per_Gallon": 26.5, "Cylinders": 4, "Displacement": 140.0, "Horsepower": 72.0, "Weight_in_lbs": 2565, "Acceleration": 13.6, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "volvo 245", "Miles_per_Gallon": 20.0, "Cylinders": 4, "Displacement": 130.0, "Horsepower": 102.0, "Weight_in_lbs": 3150, "Acceleration": 15.7, "Year": "1976-01-01T00:00:00", "Origin": "Europe"}, {"Name": "plymouth volare premier v8", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 318.0, "Horsepower": 150.0, "Weight_in_lbs": 3940, "Acceleration": 13.2, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "peugeot 504", "Miles_per_Gallon": 19.0, "Cylinders": 4, "Displacement": 120.0, "Horsepower": 88.0, "Weight_in_lbs": 3270, "Acceleration": 21.9, "Year": "1976-01-01T00:00:00", "Origin": "Europe"}, {"Name": "toyota mark ii", "Miles_per_Gallon": 19.0, "Cylinders": 6, "Displacement": 156.0, "Horsepower": 108.0, "Weight_in_lbs": 2930, "Acceleration": 15.5, "Year": "1976-01-01T00:00:00", "Origin": "Japan"}, {"Name": "mercedes-benz 280s", "Miles_per_Gallon": 16.5, "Cylinders": 6, "Displacement": 168.0, "Horsepower": 120.0, "Weight_in_lbs": 3820, "Acceleration": 16.7, "Year": "1976-01-01T00:00:00", "Origin": "Europe"}, {"Name": "cadillac seville", "Miles_per_Gallon": 16.5, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 180.0, "Weight_in_lbs": 4380, "Acceleration": 12.1, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevy c10", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 145.0, "Weight_in_lbs": 4055, "Acceleration": 12.0, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford f108", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 302.0, "Horsepower": 130.0, "Weight_in_lbs": 3870, "Acceleration": 15.0, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge d100", "Miles_per_Gallon": 13.0, "Cylinders": 8, "Displacement": 318.0, "Horsepower": 150.0, "Weight_in_lbs": 3755, "Acceleration": 14.0, "Year": "1976-01-01T00:00:00", "Origin": "USA"}, {"Name": "honda Accelerationord cvcc", "Miles_per_Gallon": 31.5, "Cylinders": 4, "Displacement": 98.0, "Horsepower": 68.0, "Weight_in_lbs": 2045, "Acceleration": 18.5, "Year": "1977-01-01T00:00:00", "Origin": "Japan"}, {"Name": "buick opel isuzu deluxe", "Miles_per_Gallon": 30.0, "Cylinders": 4, "Displacement": 111.0, "Horsepower": 80.0, "Weight_in_lbs": 2155, "Acceleration": 14.8, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "renault 5 gtl", "Miles_per_Gallon": 36.0, "Cylinders": 4, "Displacement": 79.0, "Horsepower": 58.0, "Weight_in_lbs": 1825, "Acceleration": 18.6, "Year": "1977-01-01T00:00:00", "Origin": "Europe"}, {"Name": "plymouth arrow gs", "Miles_per_Gallon": 25.5, "Cylinders": 4, "Displacement": 122.0, "Horsepower": 96.0, "Weight_in_lbs": 2300, "Acceleration": 15.5, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "datsun f-10 hatchback", "Miles_per_Gallon": 33.5, "Cylinders": 4, "Displacement": 85.0, "Horsepower": 70.0, "Weight_in_lbs": 1945, "Acceleration": 16.8, "Year": "1977-01-01T00:00:00", "Origin": "Japan"}, {"Name": "chevrolet caprice classic", "Miles_per_Gallon": 17.5, "Cylinders": 8, "Displacement": 305.0, "Horsepower": 145.0, "Weight_in_lbs": 3880, "Acceleration": 12.5, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "oldsmobile cutlass supreme", "Miles_per_Gallon": 17.0, "Cylinders": 8, "Displacement": 260.0, "Horsepower": 110.0, "Weight_in_lbs": 4060, "Acceleration": 19.0, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge monaco brougham", "Miles_per_Gallon": 15.5, "Cylinders": 8, "Displacement": 318.0, "Horsepower": 145.0, "Weight_in_lbs": 4140, "Acceleration": 13.7, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "mercury cougar brougham", "Miles_per_Gallon": 15.0, "Cylinders": 8, "Displacement": 302.0, "Horsepower": 130.0, "Weight_in_lbs": 4295, "Acceleration": 14.9, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet concours", "Miles_per_Gallon": 17.5, "Cylinders": 6, "Displacement": 250.0, "Horsepower": 110.0, "Weight_in_lbs": 3520, "Acceleration": 16.4, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "buick skylark", "Miles_per_Gallon": 20.5, "Cylinders": 6, "Displacement": 231.0, "Horsepower": 105.0, "Weight_in_lbs": 3425, "Acceleration": 16.9, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth volare custom", "Miles_per_Gallon": 19.0, "Cylinders": 6, "Displacement": 225.0, "Horsepower": 100.0, "Weight_in_lbs": 3630, "Acceleration": 17.7, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford granada", "Miles_per_Gallon": 18.5, "Cylinders": 6, "Displacement": 250.0, "Horsepower": 98.0, "Weight_in_lbs": 3525, "Acceleration": 19.0, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "pontiac grand prix lj", "Miles_per_Gallon": 16.0, "Cylinders": 8, "Displacement": 400.0, "Horsepower": 180.0, "Weight_in_lbs": 4220, "Acceleration": 11.1, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet monte carlo landau", "Miles_per_Gallon": 15.5, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 170.0, "Weight_in_lbs": 4165, "Acceleration": 11.4, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "chrysler cordoba", "Miles_per_Gallon": 15.5, "Cylinders": 8, "Displacement": 400.0, "Horsepower": 190.0, "Weight_in_lbs": 4325, "Acceleration": 12.2, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford thunderbird", "Miles_per_Gallon": 16.0, "Cylinders": 8, "Displacement": 351.0, "Horsepower": 149.0, "Weight_in_lbs": 4335, "Acceleration": 14.5, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "volkswagen rabbit custom", "Miles_per_Gallon": 29.0, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 78.0, "Weight_in_lbs": 1940, "Acceleration": 14.5, "Year": "1977-01-01T00:00:00", "Origin": "Europe"}, {"Name": "pontiac sunbird coupe", "Miles_per_Gallon": 24.5, "Cylinders": 4, "Displacement": 151.0, "Horsepower": 88.0, "Weight_in_lbs": 2740, "Acceleration": 16.0, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "toyota corolla liftback", "Miles_per_Gallon": 26.0, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 75.0, "Weight_in_lbs": 2265, "Acceleration": 18.2, "Year": "1977-01-01T00:00:00", "Origin": "Japan"}, {"Name": "ford mustang ii 2+2", "Miles_per_Gallon": 25.5, "Cylinders": 4, "Displacement": 140.0, "Horsepower": 89.0, "Weight_in_lbs": 2755, "Acceleration": 15.8, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet chevette", "Miles_per_Gallon": 30.5, "Cylinders": 4, "Displacement": 98.0, "Horsepower": 63.0, "Weight_in_lbs": 2051, "Acceleration": 17.0, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge colt m/m", "Miles_per_Gallon": 33.5, "Cylinders": 4, "Displacement": 98.0, "Horsepower": 83.0, "Weight_in_lbs": 2075, "Acceleration": 15.9, "Year": "1977-01-01T00:00:00", "Origin": "USA"}, {"Name": "subaru dl", "Miles_per_Gallon": 30.0, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 67.0, "Weight_in_lbs": 1985, "Acceleration": 16.4, "Year": "1977-01-01T00:00:00", "Origin": "Japan"}, {"Name": "volkswagen dasher", "Miles_per_Gallon": 30.5, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 78.0, "Weight_in_lbs": 2190, "Acceleration": 14.1, "Year": "1977-01-01T00:00:00", "Origin": "Europe"}, {"Name": "datsun 810", "Miles_per_Gallon": 22.0, "Cylinders": 6, "Displacement": 146.0, "Horsepower": 97.0, "Weight_in_lbs": 2815, "Acceleration": 14.5, "Year": "1977-01-01T00:00:00", "Origin": "Japan"}, {"Name": "bmw 320i", "Miles_per_Gallon": 21.5, "Cylinders": 4, "Displacement": 121.0, "Horsepower": 110.0, "Weight_in_lbs": 2600, "Acceleration": 12.8, "Year": "1977-01-01T00:00:00", "Origin": "Europe"}, {"Name": "mazda rx-4", "Miles_per_Gallon": 21.5, "Cylinders": 3, "Displacement": 80.0, "Horsepower": 110.0, "Weight_in_lbs": 2720, "Acceleration": 13.5, "Year": "1977-01-01T00:00:00", "Origin": "Japan"}, {"Name": "volkswagen rabbit custom diesel", "Miles_per_Gallon": 43.1, "Cylinders": 4, "Displacement": 90.0, "Horsepower": 48.0, "Weight_in_lbs": 1985, "Acceleration": 21.5, "Year": "1978-01-01T00:00:00", "Origin": "Europe"}, {"Name": "ford fiesta", "Miles_per_Gallon": 36.1, "Cylinders": 4, "Displacement": 98.0, "Horsepower": 66.0, "Weight_in_lbs": 1800, "Acceleration": 14.4, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "mazda glc deluxe", "Miles_per_Gallon": 32.8, "Cylinders": 4, "Displacement": 78.0, "Horsepower": 52.0, "Weight_in_lbs": 1985, "Acceleration": 19.4, "Year": "1978-01-01T00:00:00", "Origin": "Japan"}, {"Name": "datsun b210 gx", "Miles_per_Gallon": 39.4, "Cylinders": 4, "Displacement": 85.0, "Horsepower": 70.0, "Weight_in_lbs": 2070, "Acceleration": 18.6, "Year": "1978-01-01T00:00:00", "Origin": "Japan"}, {"Name": "honda civic cvcc", "Miles_per_Gallon": 36.1, "Cylinders": 4, "Displacement": 91.0, "Horsepower": 60.0, "Weight_in_lbs": 1800, "Acceleration": 16.4, "Year": "1978-01-01T00:00:00", "Origin": "Japan"}, {"Name": "oldsmobile cutlass salon brougham", "Miles_per_Gallon": 19.9, "Cylinders": 8, "Displacement": 260.0, "Horsepower": 110.0, "Weight_in_lbs": 3365, "Acceleration": 15.5, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge diplomat", "Miles_per_Gallon": 19.4, "Cylinders": 8, "Displacement": 318.0, "Horsepower": 140.0, "Weight_in_lbs": 3735, "Acceleration": 13.2, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "mercury monarch ghia", "Miles_per_Gallon": 20.2, "Cylinders": 8, "Displacement": 302.0, "Horsepower": 139.0, "Weight_in_lbs": 3570, "Acceleration": 12.8, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "pontiac phoenix lj", "Miles_per_Gallon": 19.2, "Cylinders": 6, "Displacement": 231.0, "Horsepower": 105.0, "Weight_in_lbs": 3535, "Acceleration": 19.2, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet malibu", "Miles_per_Gallon": 20.5, "Cylinders": 6, "Displacement": 200.0, "Horsepower": 95.0, "Weight_in_lbs": 3155, "Acceleration": 18.2, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford fairmont (auto)", "Miles_per_Gallon": 20.2, "Cylinders": 6, "Displacement": 200.0, "Horsepower": 85.0, "Weight_in_lbs": 2965, "Acceleration": 15.8, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford fairmont (man)", "Miles_per_Gallon": 25.1, "Cylinders": 4, "Displacement": 140.0, "Horsepower": 88.0, "Weight_in_lbs": 2720, "Acceleration": 15.4, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth volare", "Miles_per_Gallon": 20.5, "Cylinders": 6, "Displacement": 225.0, "Horsepower": 100.0, "Weight_in_lbs": 3430, "Acceleration": 17.2, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc concord", "Miles_per_Gallon": 19.4, "Cylinders": 6, "Displacement": 232.0, "Horsepower": 90.0, "Weight_in_lbs": 3210, "Acceleration": 17.2, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "buick century special", "Miles_per_Gallon": 20.6, "Cylinders": 6, "Displacement": 231.0, "Horsepower": 105.0, "Weight_in_lbs": 3380, "Acceleration": 15.8, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "mercury zephyr", "Miles_per_Gallon": 20.8, "Cylinders": 6, "Displacement": 200.0, "Horsepower": 85.0, "Weight_in_lbs": 3070, "Acceleration": 16.7, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge aspen", "Miles_per_Gallon": 18.6, "Cylinders": 6, "Displacement": 225.0, "Horsepower": 110.0, "Weight_in_lbs": 3620, "Acceleration": 18.7, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc concord d/l", "Miles_per_Gallon": 18.1, "Cylinders": 6, "Displacement": 258.0, "Horsepower": 120.0, "Weight_in_lbs": 3410, "Acceleration": 15.1, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet monte carlo landau", "Miles_per_Gallon": 19.2, "Cylinders": 8, "Displacement": 305.0, "Horsepower": 145.0, "Weight_in_lbs": 3425, "Acceleration": 13.2, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "buick regal sport coupe (turbo)", "Miles_per_Gallon": 17.7, "Cylinders": 6, "Displacement": 231.0, "Horsepower": 165.0, "Weight_in_lbs": 3445, "Acceleration": 13.4, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford futura", "Miles_per_Gallon": 18.1, "Cylinders": 8, "Displacement": 302.0, "Horsepower": 139.0, "Weight_in_lbs": 3205, "Acceleration": 11.2, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge magnum xe", "Miles_per_Gallon": 17.5, "Cylinders": 8, "Displacement": 318.0, "Horsepower": 140.0, "Weight_in_lbs": 4080, "Acceleration": 13.7, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet chevette", "Miles_per_Gallon": 30.0, "Cylinders": 4, "Displacement": 98.0, "Horsepower": 68.0, "Weight_in_lbs": 2155, "Acceleration": 16.5, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "toyota corona", "Miles_per_Gallon": 27.5, "Cylinders": 4, "Displacement": 134.0, "Horsepower": 95.0, "Weight_in_lbs": 2560, "Acceleration": 14.2, "Year": "1978-01-01T00:00:00", "Origin": "Japan"}, {"Name": "datsun 510", "Miles_per_Gallon": 27.2, "Cylinders": 4, "Displacement": 119.0, "Horsepower": 97.0, "Weight_in_lbs": 2300, "Acceleration": 14.7, "Year": "1978-01-01T00:00:00", "Origin": "Japan"}, {"Name": "dodge omni", "Miles_per_Gallon": 30.9, "Cylinders": 4, "Displacement": 105.0, "Horsepower": 75.0, "Weight_in_lbs": 2230, "Acceleration": 14.5, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "toyota celica gt liftback", "Miles_per_Gallon": 21.1, "Cylinders": 4, "Displacement": 134.0, "Horsepower": 95.0, "Weight_in_lbs": 2515, "Acceleration": 14.8, "Year": "1978-01-01T00:00:00", "Origin": "Japan"}, {"Name": "plymouth sapporo", "Miles_per_Gallon": 23.2, "Cylinders": 4, "Displacement": 156.0, "Horsepower": 105.0, "Weight_in_lbs": 2745, "Acceleration": 16.7, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "oldsmobile starfire sx", "Miles_per_Gallon": 23.8, "Cylinders": 4, "Displacement": 151.0, "Horsepower": 85.0, "Weight_in_lbs": 2855, "Acceleration": 17.6, "Year": "1978-01-01T00:00:00", "Origin": "USA"}, {"Name": "datsun 200-sx", "Miles_per_Gallon": 23.9, "Cylinders": 4, "Displacement": 119.0, "Horsepower": 97.0, "Weight_in_lbs": 2405, "Acceleration": 14.9, "Year": "1978-01-01T00:00:00", "Origin": "Japan"}, {"Name": "audi 5000", "Miles_per_Gallon": 20.3, "Cylinders": 5, "Displacement": 131.0, "Horsepower": 103.0, "Weight_in_lbs": 2830, "Acceleration": 15.9, "Year": "1978-01-01T00:00:00", "Origin": "Europe"}, {"Name": "volvo 264gl", "Miles_per_Gallon": 17.0, "Cylinders": 6, "Displacement": 163.0, "Horsepower": 125.0, "Weight_in_lbs": 3140, "Acceleration": 13.6, "Year": "1978-01-01T00:00:00", "Origin": "Europe"}, {"Name": "saab 99gle", "Miles_per_Gallon": 21.6, "Cylinders": 4, "Displacement": 121.0, "Horsepower": 115.0, "Weight_in_lbs": 2795, "Acceleration": 15.7, "Year": "1978-01-01T00:00:00", "Origin": "Europe"}, {"Name": "peugeot 604sl", "Miles_per_Gallon": 16.2, "Cylinders": 6, "Displacement": 163.0, "Horsepower": 133.0, "Weight_in_lbs": 3410, "Acceleration": 15.8, "Year": "1978-01-01T00:00:00", "Origin": "Europe"}, {"Name": "volkswagen scirocco", "Miles_per_Gallon": 31.5, "Cylinders": 4, "Displacement": 89.0, "Horsepower": 71.0, "Weight_in_lbs": 1990, "Acceleration": 14.9, "Year": "1978-01-01T00:00:00", "Origin": "Europe"}, {"Name": "honda Accelerationord lx", "Miles_per_Gallon": 29.5, "Cylinders": 4, "Displacement": 98.0, "Horsepower": 68.0, "Weight_in_lbs": 2135, "Acceleration": 16.6, "Year": "1978-01-01T00:00:00", "Origin": "Japan"}, {"Name": "pontiac lemans v6", "Miles_per_Gallon": 21.5, "Cylinders": 6, "Displacement": 231.0, "Horsepower": 115.0, "Weight_in_lbs": 3245, "Acceleration": 15.4, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "mercury zephyr 6", "Miles_per_Gallon": 19.8, "Cylinders": 6, "Displacement": 200.0, "Horsepower": 85.0, "Weight_in_lbs": 2990, "Acceleration": 18.2, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford fairmont 4", "Miles_per_Gallon": 22.3, "Cylinders": 4, "Displacement": 140.0, "Horsepower": 88.0, "Weight_in_lbs": 2890, "Acceleration": 17.3, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc concord dl 6", "Miles_per_Gallon": 20.2, "Cylinders": 6, "Displacement": 232.0, "Horsepower": 90.0, "Weight_in_lbs": 3265, "Acceleration": 18.2, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge aspen 6", "Miles_per_Gallon": 20.6, "Cylinders": 6, "Displacement": 225.0, "Horsepower": 110.0, "Weight_in_lbs": 3360, "Acceleration": 16.6, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet caprice classic", "Miles_per_Gallon": 17.0, "Cylinders": 8, "Displacement": 305.0, "Horsepower": 130.0, "Weight_in_lbs": 3840, "Acceleration": 15.4, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford ltd landau", "Miles_per_Gallon": 17.6, "Cylinders": 8, "Displacement": 302.0, "Horsepower": 129.0, "Weight_in_lbs": 3725, "Acceleration": 13.4, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "mercury grand marquis", "Miles_per_Gallon": 16.5, "Cylinders": 8, "Displacement": 351.0, "Horsepower": 138.0, "Weight_in_lbs": 3955, "Acceleration": 13.2, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge st. regis", "Miles_per_Gallon": 18.2, "Cylinders": 8, "Displacement": 318.0, "Horsepower": 135.0, "Weight_in_lbs": 3830, "Acceleration": 15.2, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "buick estate wagon (sw)", "Miles_per_Gallon": 16.9, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 155.0, "Weight_in_lbs": 4360, "Acceleration": 14.9, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford country squire (sw)", "Miles_per_Gallon": 15.5, "Cylinders": 8, "Displacement": 351.0, "Horsepower": 142.0, "Weight_in_lbs": 4054, "Acceleration": 14.3, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet malibu classic (sw)", "Miles_per_Gallon": 19.2, "Cylinders": 8, "Displacement": 267.0, "Horsepower": 125.0, "Weight_in_lbs": 3605, "Acceleration": 15.0, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "chrysler lebaron town @ country (sw)", "Miles_per_Gallon": 18.5, "Cylinders": 8, "Displacement": 360.0, "Horsepower": 150.0, "Weight_in_lbs": 3940, "Acceleration": 13.0, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "vw rabbit custom", "Miles_per_Gallon": 31.9, "Cylinders": 4, "Displacement": 89.0, "Horsepower": 71.0, "Weight_in_lbs": 1925, "Acceleration": 14.0, "Year": "1979-01-01T00:00:00", "Origin": "Europe"}, {"Name": "maxda glc deluxe", "Miles_per_Gallon": 34.1, "Cylinders": 4, "Displacement": 86.0, "Horsepower": 65.0, "Weight_in_lbs": 1975, "Acceleration": 15.2, "Year": "1979-01-01T00:00:00", "Origin": "Japan"}, {"Name": "dodge colt hatchback custom", "Miles_per_Gallon": 35.7, "Cylinders": 4, "Displacement": 98.0, "Horsepower": 80.0, "Weight_in_lbs": 1915, "Acceleration": 14.4, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc spirit dl", "Miles_per_Gallon": 27.4, "Cylinders": 4, "Displacement": 121.0, "Horsepower": 80.0, "Weight_in_lbs": 2670, "Acceleration": 15.0, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "mercedes benz 300d", "Miles_per_Gallon": 25.4, "Cylinders": 5, "Displacement": 183.0, "Horsepower": 77.0, "Weight_in_lbs": 3530, "Acceleration": 20.1, "Year": "1979-01-01T00:00:00", "Origin": "Europe"}, {"Name": "cadillac eldorado", "Miles_per_Gallon": 23.0, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 125.0, "Weight_in_lbs": 3900, "Acceleration": 17.4, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "peugeot 504", "Miles_per_Gallon": 27.2, "Cylinders": 4, "Displacement": 141.0, "Horsepower": 71.0, "Weight_in_lbs": 3190, "Acceleration": 24.8, "Year": "1979-01-01T00:00:00", "Origin": "Europe"}, {"Name": "oldsmobile cutlass salon brougham", "Miles_per_Gallon": 23.9, "Cylinders": 8, "Displacement": 260.0, "Horsepower": 90.0, "Weight_in_lbs": 3420, "Acceleration": 22.2, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth horizon", "Miles_per_Gallon": 34.2, "Cylinders": 4, "Displacement": 105.0, "Horsepower": 70.0, "Weight_in_lbs": 2200, "Acceleration": 13.2, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth horizon tc3", "Miles_per_Gallon": 34.5, "Cylinders": 4, "Displacement": 105.0, "Horsepower": 70.0, "Weight_in_lbs": 2150, "Acceleration": 14.9, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "datsun 210", "Miles_per_Gallon": 31.8, "Cylinders": 4, "Displacement": 85.0, "Horsepower": 65.0, "Weight_in_lbs": 2020, "Acceleration": 19.2, "Year": "1979-01-01T00:00:00", "Origin": "Japan"}, {"Name": "fiat strada custom", "Miles_per_Gallon": 37.3, "Cylinders": 4, "Displacement": 91.0, "Horsepower": 69.0, "Weight_in_lbs": 2130, "Acceleration": 14.7, "Year": "1979-01-01T00:00:00", "Origin": "Europe"}, {"Name": "buick skylark limited", "Miles_per_Gallon": 28.4, "Cylinders": 4, "Displacement": 151.0, "Horsepower": 90.0, "Weight_in_lbs": 2670, "Acceleration": 16.0, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet citation", "Miles_per_Gallon": 28.8, "Cylinders": 6, "Displacement": 173.0, "Horsepower": 115.0, "Weight_in_lbs": 2595, "Acceleration": 11.3, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "oldsmobile omega brougham", "Miles_per_Gallon": 26.8, "Cylinders": 6, "Displacement": 173.0, "Horsepower": 115.0, "Weight_in_lbs": 2700, "Acceleration": 12.9, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "pontiac phoenix", "Miles_per_Gallon": 33.5, "Cylinders": 4, "Displacement": 151.0, "Horsepower": 90.0, "Weight_in_lbs": 2556, "Acceleration": 13.2, "Year": "1979-01-01T00:00:00", "Origin": "USA"}, {"Name": "vw rabbit", "Miles_per_Gallon": 41.5, "Cylinders": 4, "Displacement": 98.0, "Horsepower": 76.0, "Weight_in_lbs": 2144, "Acceleration": 14.7, "Year": "1980-01-01T00:00:00", "Origin": "Europe"}, {"Name": "toyota corolla tercel", "Miles_per_Gallon": 38.1, "Cylinders": 4, "Displacement": 89.0, "Horsepower": 60.0, "Weight_in_lbs": 1968, "Acceleration": 18.8, "Year": "1980-01-01T00:00:00", "Origin": "Japan"}, {"Name": "chevrolet chevette", "Miles_per_Gallon": 32.1, "Cylinders": 4, "Displacement": 98.0, "Horsepower": 70.0, "Weight_in_lbs": 2120, "Acceleration": 15.5, "Year": "1980-01-01T00:00:00", "Origin": "USA"}, {"Name": "datsun 310", "Miles_per_Gallon": 37.2, "Cylinders": 4, "Displacement": 86.0, "Horsepower": 65.0, "Weight_in_lbs": 2019, "Acceleration": 16.4, "Year": "1980-01-01T00:00:00", "Origin": "Japan"}, {"Name": "chevrolet citation", "Miles_per_Gallon": 28.0, "Cylinders": 4, "Displacement": 151.0, "Horsepower": 90.0, "Weight_in_lbs": 2678, "Acceleration": 16.5, "Year": "1980-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford fairmont", "Miles_per_Gallon": 26.4, "Cylinders": 4, "Displacement": 140.0, "Horsepower": 88.0, "Weight_in_lbs": 2870, "Acceleration": 18.1, "Year": "1980-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc concord", "Miles_per_Gallon": 24.3, "Cylinders": 4, "Displacement": 151.0, "Horsepower": 90.0, "Weight_in_lbs": 3003, "Acceleration": 20.1, "Year": "1980-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge aspen", "Miles_per_Gallon": 19.1, "Cylinders": 6, "Displacement": 225.0, "Horsepower": 90.0, "Weight_in_lbs": 3381, "Acceleration": 18.7, "Year": "1980-01-01T00:00:00", "Origin": "USA"}, {"Name": "audi 4000", "Miles_per_Gallon": 34.3, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 78.0, "Weight_in_lbs": 2188, "Acceleration": 15.8, "Year": "1980-01-01T00:00:00", "Origin": "Europe"}, {"Name": "toyota corona liftback", "Miles_per_Gallon": 29.8, "Cylinders": 4, "Displacement": 134.0, "Horsepower": 90.0, "Weight_in_lbs": 2711, "Acceleration": 15.5, "Year": "1980-01-01T00:00:00", "Origin": "Japan"}, {"Name": "mazda 626", "Miles_per_Gallon": 31.3, "Cylinders": 4, "Displacement": 120.0, "Horsepower": 75.0, "Weight_in_lbs": 2542, "Acceleration": 17.5, "Year": "1980-01-01T00:00:00", "Origin": "Japan"}, {"Name": "datsun 510 hatchback", "Miles_per_Gallon": 37.0, "Cylinders": 4, "Displacement": 119.0, "Horsepower": 92.0, "Weight_in_lbs": 2434, "Acceleration": 15.0, "Year": "1980-01-01T00:00:00", "Origin": "Japan"}, {"Name": "toyota corolla", "Miles_per_Gallon": 32.2, "Cylinders": 4, "Displacement": 108.0, "Horsepower": 75.0, "Weight_in_lbs": 2265, "Acceleration": 15.2, "Year": "1980-01-01T00:00:00", "Origin": "Japan"}, {"Name": "mazda glc", "Miles_per_Gallon": 46.6, "Cylinders": 4, "Displacement": 86.0, "Horsepower": 65.0, "Weight_in_lbs": 2110, "Acceleration": 17.9, "Year": "1980-01-01T00:00:00", "Origin": "Japan"}, {"Name": "dodge colt", "Miles_per_Gallon": 27.9, "Cylinders": 4, "Displacement": 156.0, "Horsepower": 105.0, "Weight_in_lbs": 2800, "Acceleration": 14.4, "Year": "1980-01-01T00:00:00", "Origin": "USA"}, {"Name": "datsun 210", "Miles_per_Gallon": 40.8, "Cylinders": 4, "Displacement": 85.0, "Horsepower": 65.0, "Weight_in_lbs": 2110, "Acceleration": 19.2, "Year": "1980-01-01T00:00:00", "Origin": "Japan"}, {"Name": "vw rabbit c (diesel)", "Miles_per_Gallon": 44.3, "Cylinders": 4, "Displacement": 90.0, "Horsepower": 48.0, "Weight_in_lbs": 2085, "Acceleration": 21.7, "Year": "1980-01-01T00:00:00", "Origin": "Europe"}, {"Name": "vw dasher (diesel)", "Miles_per_Gallon": 43.4, "Cylinders": 4, "Displacement": 90.0, "Horsepower": 48.0, "Weight_in_lbs": 2335, "Acceleration": 23.7, "Year": "1980-01-01T00:00:00", "Origin": "Europe"}, {"Name": "audi 5000s (diesel)", "Miles_per_Gallon": 36.4, "Cylinders": 5, "Displacement": 121.0, "Horsepower": 67.0, "Weight_in_lbs": 2950, "Acceleration": 19.9, "Year": "1980-01-01T00:00:00", "Origin": "Europe"}, {"Name": "mercedes-benz 240d", "Miles_per_Gallon": 30.0, "Cylinders": 4, "Displacement": 146.0, "Horsepower": 67.0, "Weight_in_lbs": 3250, "Acceleration": 21.8, "Year": "1980-01-01T00:00:00", "Origin": "Europe"}, {"Name": "honda civic 1500 gl", "Miles_per_Gallon": 44.6, "Cylinders": 4, "Displacement": 91.0, "Horsepower": 67.0, "Weight_in_lbs": 1850, "Acceleration": 13.8, "Year": "1980-01-01T00:00:00", "Origin": "Japan"}, {"Name": "renault lecar deluxe", "Miles_per_Gallon": 40.9, "Cylinders": 4, "Displacement": 85.0, "Horsepower": null, "Weight_in_lbs": 1835, "Acceleration": 17.3, "Year": "1980-01-01T00:00:00", "Origin": "Europe"}, {"Name": "subaru dl", "Miles_per_Gallon": 33.8, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 67.0, "Weight_in_lbs": 2145, "Acceleration": 18.0, "Year": "1980-01-01T00:00:00", "Origin": "Japan"}, {"Name": "vokswagen rabbit", "Miles_per_Gallon": 29.8, "Cylinders": 4, "Displacement": 89.0, "Horsepower": 62.0, "Weight_in_lbs": 1845, "Acceleration": 15.3, "Year": "1980-01-01T00:00:00", "Origin": "Europe"}, {"Name": "datsun 280-zx", "Miles_per_Gallon": 32.7, "Cylinders": 6, "Displacement": 168.0, "Horsepower": 132.0, "Weight_in_lbs": 2910, "Acceleration": 11.4, "Year": "1980-01-01T00:00:00", "Origin": "Japan"}, {"Name": "mazda rx-7 gs", "Miles_per_Gallon": 23.7, "Cylinders": 3, "Displacement": 70.0, "Horsepower": 100.0, "Weight_in_lbs": 2420, "Acceleration": 12.5, "Year": "1980-01-01T00:00:00", "Origin": "Japan"}, {"Name": "triumph tr7 coupe", "Miles_per_Gallon": 35.0, "Cylinders": 4, "Displacement": 122.0, "Horsepower": 88.0, "Weight_in_lbs": 2500, "Acceleration": 15.1, "Year": "1980-01-01T00:00:00", "Origin": "Europe"}, {"Name": "ford mustang cobra", "Miles_per_Gallon": 23.6, "Cylinders": 4, "Displacement": 140.0, "Horsepower": null, "Weight_in_lbs": 2905, "Acceleration": 14.3, "Year": "1980-01-01T00:00:00", "Origin": "USA"}, {"Name": "honda Accelerationord", "Miles_per_Gallon": 32.4, "Cylinders": 4, "Displacement": 107.0, "Horsepower": 72.0, "Weight_in_lbs": 2290, "Acceleration": 17.0, "Year": "1980-01-01T00:00:00", "Origin": "Japan"}, {"Name": "plymouth reliant", "Miles_per_Gallon": 27.2, "Cylinders": 4, "Displacement": 135.0, "Horsepower": 84.0, "Weight_in_lbs": 2490, "Acceleration": 15.7, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "buick skylark", "Miles_per_Gallon": 26.6, "Cylinders": 4, "Displacement": 151.0, "Horsepower": 84.0, "Weight_in_lbs": 2635, "Acceleration": 16.4, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge aries wagon (sw)", "Miles_per_Gallon": 25.8, "Cylinders": 4, "Displacement": 156.0, "Horsepower": 92.0, "Weight_in_lbs": 2620, "Acceleration": 14.4, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet citation", "Miles_per_Gallon": 23.5, "Cylinders": 6, "Displacement": 173.0, "Horsepower": 110.0, "Weight_in_lbs": 2725, "Acceleration": 12.6, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "plymouth reliant", "Miles_per_Gallon": 30.0, "Cylinders": 4, "Displacement": 135.0, "Horsepower": 84.0, "Weight_in_lbs": 2385, "Acceleration": 12.9, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "toyota starlet", "Miles_per_Gallon": 39.1, "Cylinders": 4, "Displacement": 79.0, "Horsepower": 58.0, "Weight_in_lbs": 1755, "Acceleration": 16.9, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "plymouth champ", "Miles_per_Gallon": 39.0, "Cylinders": 4, "Displacement": 86.0, "Horsepower": 64.0, "Weight_in_lbs": 1875, "Acceleration": 16.4, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "honda civic 1300", "Miles_per_Gallon": 35.1, "Cylinders": 4, "Displacement": 81.0, "Horsepower": 60.0, "Weight_in_lbs": 1760, "Acceleration": 16.1, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "subaru", "Miles_per_Gallon": 32.3, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 67.0, "Weight_in_lbs": 2065, "Acceleration": 17.8, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "datsun 210", "Miles_per_Gallon": 37.0, "Cylinders": 4, "Displacement": 85.0, "Horsepower": 65.0, "Weight_in_lbs": 1975, "Acceleration": 19.4, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "toyota tercel", "Miles_per_Gallon": 37.7, "Cylinders": 4, "Displacement": 89.0, "Horsepower": 62.0, "Weight_in_lbs": 2050, "Acceleration": 17.3, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "mazda glc 4", "Miles_per_Gallon": 34.1, "Cylinders": 4, "Displacement": 91.0, "Horsepower": 68.0, "Weight_in_lbs": 1985, "Acceleration": 16.0, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "plymouth horizon 4", "Miles_per_Gallon": 34.7, "Cylinders": 4, "Displacement": 105.0, "Horsepower": 63.0, "Weight_in_lbs": 2215, "Acceleration": 14.9, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford escort 4w", "Miles_per_Gallon": 34.4, "Cylinders": 4, "Displacement": 98.0, "Horsepower": 65.0, "Weight_in_lbs": 2045, "Acceleration": 16.2, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford escort 2h", "Miles_per_Gallon": 29.9, "Cylinders": 4, "Displacement": 98.0, "Horsepower": 65.0, "Weight_in_lbs": 2380, "Acceleration": 20.7, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "volkswagen jetta", "Miles_per_Gallon": 33.0, "Cylinders": 4, "Displacement": 105.0, "Horsepower": 74.0, "Weight_in_lbs": 2190, "Acceleration": 14.2, "Year": "1982-01-01T00:00:00", "Origin": "Europe"}, {"Name": "renault 18i", "Miles_per_Gallon": 34.5, "Cylinders": 4, "Displacement": 100.0, "Horsepower": null, "Weight_in_lbs": 2320, "Acceleration": 15.8, "Year": "1982-01-01T00:00:00", "Origin": "Europe"}, {"Name": "honda prelude", "Miles_per_Gallon": 33.7, "Cylinders": 4, "Displacement": 107.0, "Horsepower": 75.0, "Weight_in_lbs": 2210, "Acceleration": 14.4, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "toyota corolla", "Miles_per_Gallon": 32.4, "Cylinders": 4, "Displacement": 108.0, "Horsepower": 75.0, "Weight_in_lbs": 2350, "Acceleration": 16.8, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "datsun 200sx", "Miles_per_Gallon": 32.9, "Cylinders": 4, "Displacement": 119.0, "Horsepower": 100.0, "Weight_in_lbs": 2615, "Acceleration": 14.8, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "mazda 626", "Miles_per_Gallon": 31.6, "Cylinders": 4, "Displacement": 120.0, "Horsepower": 74.0, "Weight_in_lbs": 2635, "Acceleration": 18.3, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "peugeot 505s turbo diesel", "Miles_per_Gallon": 28.1, "Cylinders": 4, "Displacement": 141.0, "Horsepower": 80.0, "Weight_in_lbs": 3230, "Acceleration": 20.4, "Year": "1982-01-01T00:00:00", "Origin": "Europe"}, {"Name": "saab 900s", "Miles_per_Gallon": null, "Cylinders": 4, "Displacement": 121.0, "Horsepower": 110.0, "Weight_in_lbs": 2800, "Acceleration": 15.4, "Year": "1982-01-01T00:00:00", "Origin": "Europe"}, {"Name": "volvo diesel", "Miles_per_Gallon": 30.7, "Cylinders": 6, "Displacement": 145.0, "Horsepower": 76.0, "Weight_in_lbs": 3160, "Acceleration": 19.6, "Year": "1982-01-01T00:00:00", "Origin": "Europe"}, {"Name": "toyota cressida", "Miles_per_Gallon": 25.4, "Cylinders": 6, "Displacement": 168.0, "Horsepower": 116.0, "Weight_in_lbs": 2900, "Acceleration": 12.6, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "datsun 810 maxima", "Miles_per_Gallon": 24.2, "Cylinders": 6, "Displacement": 146.0, "Horsepower": 120.0, "Weight_in_lbs": 2930, "Acceleration": 13.8, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "buick century", "Miles_per_Gallon": 22.4, "Cylinders": 6, "Displacement": 231.0, "Horsepower": 110.0, "Weight_in_lbs": 3415, "Acceleration": 15.8, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "oldsmobile cutlass ls", "Miles_per_Gallon": 26.6, "Cylinders": 8, "Displacement": 350.0, "Horsepower": 105.0, "Weight_in_lbs": 3725, "Acceleration": 19.0, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford granada gl", "Miles_per_Gallon": 20.2, "Cylinders": 6, "Displacement": 200.0, "Horsepower": 88.0, "Weight_in_lbs": 3060, "Acceleration": 17.1, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "chrysler lebaron salon", "Miles_per_Gallon": 17.6, "Cylinders": 6, "Displacement": 225.0, "Horsepower": 85.0, "Weight_in_lbs": 3465, "Acceleration": 16.6, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet cavalier", "Miles_per_Gallon": 28.0, "Cylinders": 4, "Displacement": 112.0, "Horsepower": 88.0, "Weight_in_lbs": 2605, "Acceleration": 19.6, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet cavalier wagon", "Miles_per_Gallon": 27.0, "Cylinders": 4, "Displacement": 112.0, "Horsepower": 88.0, "Weight_in_lbs": 2640, "Acceleration": 18.6, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet cavalier 2-door", "Miles_per_Gallon": 34.0, "Cylinders": 4, "Displacement": 112.0, "Horsepower": 88.0, "Weight_in_lbs": 2395, "Acceleration": 18.0, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "pontiac j2000 se hatchback", "Miles_per_Gallon": 31.0, "Cylinders": 4, "Displacement": 112.0, "Horsepower": 85.0, "Weight_in_lbs": 2575, "Acceleration": 16.2, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "dodge aries se", "Miles_per_Gallon": 29.0, "Cylinders": 4, "Displacement": 135.0, "Horsepower": 84.0, "Weight_in_lbs": 2525, "Acceleration": 16.0, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "pontiac phoenix", "Miles_per_Gallon": 27.0, "Cylinders": 4, "Displacement": 151.0, "Horsepower": 90.0, "Weight_in_lbs": 2735, "Acceleration": 18.0, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford fairmont futura", "Miles_per_Gallon": 24.0, "Cylinders": 4, "Displacement": 140.0, "Horsepower": 92.0, "Weight_in_lbs": 2865, "Acceleration": 16.4, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "amc concord dl", "Miles_per_Gallon": 23.0, "Cylinders": 4, "Displacement": 151.0, "Horsepower": null, "Weight_in_lbs": 3035, "Acceleration": 20.5, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "volkswagen rabbit l", "Miles_per_Gallon": 36.0, "Cylinders": 4, "Displacement": 105.0, "Horsepower": 74.0, "Weight_in_lbs": 1980, "Acceleration": 15.3, "Year": "1982-01-01T00:00:00", "Origin": "Europe"}, {"Name": "mazda glc custom l", "Miles_per_Gallon": 37.0, "Cylinders": 4, "Displacement": 91.0, "Horsepower": 68.0, "Weight_in_lbs": 2025, "Acceleration": 18.2, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "mazda glc custom", "Miles_per_Gallon": 31.0, "Cylinders": 4, "Displacement": 91.0, "Horsepower": 68.0, "Weight_in_lbs": 1970, "Acceleration": 17.6, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "plymouth horizon miser", "Miles_per_Gallon": 38.0, "Cylinders": 4, "Displacement": 105.0, "Horsepower": 63.0, "Weight_in_lbs": 2125, "Acceleration": 14.7, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "mercury lynx l", "Miles_per_Gallon": 36.0, "Cylinders": 4, "Displacement": 98.0, "Horsepower": 70.0, "Weight_in_lbs": 2125, "Acceleration": 17.3, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "nissan stanza xe", "Miles_per_Gallon": 36.0, "Cylinders": 4, "Displacement": 120.0, "Horsepower": 88.0, "Weight_in_lbs": 2160, "Acceleration": 14.5, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "honda Accelerationord", "Miles_per_Gallon": 36.0, "Cylinders": 4, "Displacement": 107.0, "Horsepower": 75.0, "Weight_in_lbs": 2205, "Acceleration": 14.5, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "toyota corolla", "Miles_per_Gallon": 34.0, "Cylinders": 4, "Displacement": 108.0, "Horsepower": 70.0, "Weight_in_lbs": 2245, "Acceleration": 16.9, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "honda civic", "Miles_per_Gallon": 38.0, "Cylinders": 4, "Displacement": 91.0, "Horsepower": 67.0, "Weight_in_lbs": 1965, "Acceleration": 15.0, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "honda civic (auto)", "Miles_per_Gallon": 32.0, "Cylinders": 4, "Displacement": 91.0, "Horsepower": 67.0, "Weight_in_lbs": 1965, "Acceleration": 15.7, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "datsun 310 gx", "Miles_per_Gallon": 38.0, "Cylinders": 4, "Displacement": 91.0, "Horsepower": 67.0, "Weight_in_lbs": 1995, "Acceleration": 16.2, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "buick century limited", "Miles_per_Gallon": 25.0, "Cylinders": 6, "Displacement": 181.0, "Horsepower": 110.0, "Weight_in_lbs": 2945, "Acceleration": 16.4, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "oldsmobile cutlass ciera (diesel)", "Miles_per_Gallon": 38.0, "Cylinders": 6, "Displacement": 262.0, "Horsepower": 85.0, "Weight_in_lbs": 3015, "Acceleration": 17.0, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "chrysler lebaron medallion", "Miles_per_Gallon": 26.0, "Cylinders": 4, "Displacement": 156.0, "Horsepower": 92.0, "Weight_in_lbs": 2585, "Acceleration": 14.5, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford granada l", "Miles_per_Gallon": 22.0, "Cylinders": 6, "Displacement": 232.0, "Horsepower": 112.0, "Weight_in_lbs": 2835, "Acceleration": 14.7, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "toyota celica gt", "Miles_per_Gallon": 32.0, "Cylinders": 4, "Displacement": 144.0, "Horsepower": 96.0, "Weight_in_lbs": 2665, "Acceleration": 13.9, "Year": "1982-01-01T00:00:00", "Origin": "Japan"}, {"Name": "dodge charger 2.2", "Miles_per_Gallon": 36.0, "Cylinders": 4, "Displacement": 135.0, "Horsepower": 84.0, "Weight_in_lbs": 2370, "Acceleration": 13.0, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevrolet camaro", "Miles_per_Gallon": 27.0, "Cylinders": 4, "Displacement": 151.0, "Horsepower": 90.0, "Weight_in_lbs": 2950, "Acceleration": 17.3, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford mustang gl", "Miles_per_Gallon": 27.0, "Cylinders": 4, "Displacement": 140.0, "Horsepower": 86.0, "Weight_in_lbs": 2790, "Acceleration": 15.6, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "vw pickup", "Miles_per_Gallon": 44.0, "Cylinders": 4, "Displacement": 97.0, "Horsepower": 52.0, "Weight_in_lbs": 2130, "Acceleration": 24.6, "Year": "1982-01-01T00:00:00", "Origin": "Europe"}, {"Name": "dodge rampage", "Miles_per_Gallon": 32.0, "Cylinders": 4, "Displacement": 135.0, "Horsepower": 84.0, "Weight_in_lbs": 2295, "Acceleration": 11.6, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "ford ranger", "Miles_per_Gallon": 28.0, "Cylinders": 4, "Displacement": 120.0, "Horsepower": 79.0, "Weight_in_lbs": 2625, "Acceleration": 18.6, "Year": "1982-01-01T00:00:00", "Origin": "USA"}, {"Name": "chevy s-10", "Miles_per_Gallon": 31.0, "Cylinders": 4, "Displacement": 119.0, "Horsepower": 82.0, "Weight_in_lbs": 2720, "Acceleration": 19.4, "Year": "1982-01-01T00:00:00", "Origin": "USA"}]}}, {"mode": "vega-lite"});
</script>



For more examples of Altair plots, see the [Altair snippets notebook](/notebooks/snippets/altair.ipynb) or the external [Altair Example Gallery](https://altair-viz.github.io/gallery/).

## Plotly

### Sample


```
from plotly.offline import iplot
import plotly.graph_objs as go

data = [
    go.Contour(
        z=[[10, 10.625, 12.5, 15.625, 20],
           [5.625, 6.25, 8.125, 11.25, 15.625],
           [2.5, 3.125, 5., 8.125, 12.5],
           [0.625, 1.25, 3.125, 6.25, 10.625],
           [0, 0.625, 2.5, 5.625, 10]]
    )
]
iplot(data)
```



<script src="/static/components/requirejs/require.js"></script>




        <script type="text/javascript">
        window.PlotlyConfig = {MathJaxConfig: 'local'};
        if (window.MathJax) {MathJax.Hub.Config({SVG: {font: "STIX-Web"}});}
        if (typeof require !== 'undefined') {
        require.undef("plotly");
        define('plotly', function(require, exports, module) {
            /**
* plotly.js v1.49.4
* Copyright 2012-2019, Plotly, Inc.
* All rights reserved.
* Licensed under the MIT license
*/
        });
        require(['plotly'], function(Plotly) {
            window._Plotly = Plotly;
        });
        }
        </script>




<div>


            <div id="582affae-0e8e-4cdc-8e29-5503ced18b39" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("582affae-0e8e-4cdc-8e29-5503ced18b39")) {
                    Plotly.newPlot(
                        '582affae-0e8e-4cdc-8e29-5503ced18b39',
                        [{"type": "contour", "z": [[10, 10.625, 12.5, 15.625, 20], [5.625, 6.25, 8.125, 11.25, 15.625], [2.5, 3.125, 5.0, 8.125, 12.5], [0.625, 1.25, 3.125, 6.25, 10.625], [0, 0.625, 2.5, 5.625, 10]]}],
                        {"template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "zerolinecolor": "white", "zerolinewidth": 2}}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('582affae-0e8e-4cdc-8e29-5503ced18b39');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>


## Bokeh

### Sample


```
import numpy as np
from bokeh.plotting import figure, show
from bokeh.io import output_notebook

# Call once to configure Bokeh to display plots inline in the notebook.
output_notebook()
```


```
N = 4000
x = np.random.random(size=N) * 100
y = np.random.random(size=N) * 100
radii = np.random.random(size=N) * 1.5
colors = ["#%02x%02x%02x" % (r, g, 150) for r, g in zip(np.floor(50+2*x).astype(int), np.floor(30+2*y).astype(int))]

p = figure()
p.circle(x, y, radius=radii, fill_color=colors, fill_alpha=0.6, line_color=None)
show(p)
```










<div class="bk-root" id="7bced306-38b5-4ba7-8f97-4464324548b4" data-root-id="1002"></div>



