《复杂系统入门与实战(Python)》

作业1：Python代码参考

===========

::


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
        
        
  def align_face_i(birds, i, R):  # 第i只鸟改变方向，面向另外一只鸟。根据此函数更新
      # 需要你自己去写这个函数
      # ???


  def align_angle_i(birds, i, R):  # 第i只鸟改变方向，跟另外一只鸟的方向对齐。根据此函数更新
      # 需要你自己去写这个函数
      # ???


  def move(birds, i, dt, worldlimit):  # 第i只鸟根据自己原来的方向运动
      # 需要你自己去写这个函数
      # ???
      
      
      
  worldSize = 100
  T0 = 500
  dt = 1

  R = 10  # 设定周遭范围
  v0 = 2
  N = 10 # number of birds


  birds = []
  for i in range(N): # 初始化
      birds.append( BIRD(random.random() * worldSize, random.random() * worldSize, 
                         random.random() * 2 * math.pi, v0) )
                         
                         
  def update(time, birds, R, worldSize, dt): # 每一时刻根据此函数更新
      plt.clf()

      for bird in birds:
          plt.plot([bird.x, bird.x + 2*bird.v * math.cos(bird.theta)], 
                   [bird.y, bird.y + 2*bird.v * math.sin(bird.theta)], color='r')
          plt.plot(bird.x, bird.y, 'o', color='k')

      plt.xlim(0, worldSize)
      plt.ylim(0, worldSize)
      plt.gca().set_aspect('equal') 

      for i in range(len(birds)):
          # 这里需要你自己写
          # ???

          # 以概率p对准另外一只鸟
          # align_face_i(birds, i, R)

          # 以概率q对齐另外一只鸟的方向
          # align_angle_i(birds, i, R)

          # 以概率1-p-q按原来的方向运动
          # move(birds, i, dt, worldlimit)
        
        
        
  fig, ax = plt.subplots(1, figsize=(8,8), dpi=60)  # 初始化世界，画图

  ani = matplotlib.animation.FuncAnimation(fig, update, frames=T0, fargs=[birds, R, worldSize, dt]) # 主函数，设置更新函数
  # 这其中的 update() 是一个函数，其自变量由 fargs 给出
  # update()的第一个变量一定是time，而 fargs 中从第二个自变量开始写起

  ani.save('SPP_movie.mp4', writer='ffmpeg', fps=30)  # 储存动画
