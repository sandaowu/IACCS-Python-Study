《复杂科学简介》Vicsek模型（动画）
===========

课程视频在B站
用 Python 从零开始编写 Vicsek模型，模拟群体动物行为::


  import matplotlib.animation
  import matplotlib.pyplot as plt
  import random
  import math
  import numpy as np
  
  class BIRD(object):
    def __init__(self, x, y, theta, v0):
        self.x = x
        self.y = y
        self.theta = theta
        self.v = v0
        self.old_theta = theta
        
    def move(self, dt, worldlimit):
        self.x += self.v * math.cos(self.theta) * dt
        self.y += self.v * math.sin(self.theta) * dt
        self.x = self.x % worldlimit
        self.y = self.y % worldlimit
        
        
  def align_i(brids, i, Rsquare):
    x = birds[i].x
    y = birds[i].y
    neighbors = []
    for j in range(len(birds)):
        if j != i:
            if (birds[j].x - x)**2 + (birds[j].y - y)**2 <= Rsquare:
                neighbors.append(j)
    # neighbors.append(i)
    if len(neighbors) != 0:
        tempx, tempy = 0, 0
        for k in neighbors:
            tempy += math.sin(birds[k].old_theta)
            tempx += math.cos(birds[k].old_theta)

        birds[i].old_theta = birds[i].theta
        if tempx < 0:
            birds[i].theta = math.atan(tempy/tempx) + math.pi
        else:
            birds[i].theta = math.atan(tempy/tempx)
            
            
  def DrawBirds(birds, worldlimit):
    for bird in birds:
        plt.plot([bird.x, bird.x + 2*bird.v * math.cos(bird.theta)], 
                 [bird.y, bird.y + 2*bird.v * math.sin(bird.theta)], color='r')
        plt.plot(bird.x, bird.y, 'o', color='k')
        
    plt.xlim(0, worldlimit)
    plt.ylim(0, worldlimit)
    plt.gca().set_aspect('equal')    


  def update(time, birds, worldlimit):
    plt.clf()
    ax = plt.gca()
    DrawBirds(birds, worldlimit)
    for i in range(N):
        birds[i].move(dt, worldlimit)
        align_i(birds, i, worldlimit)
        
        
  N = 10 # number of birds
  worldlimit = 100
  v0 = 2
  T0 = 500

  dt = 1
  birds = []
  for i in range(N):
      birds.append( BIRD(random.random() * worldlimit, random.random() * worldlimit, 
                         random.random() * 2 * math.pi, v0) )
  
  
  fig, ax = plt.subplots(1, figsize=(8,8), dpi=60)

  ani = matplotlib.animation.FuncAnimation(fig, update, frames=T0, fargs=[birds, worldlimit])

  Writer = matplotlib.animation.writers['ffmpeg']
  writer = Writer(fps = 30)
  ani.save('data.mp4', writer=writer)
  
