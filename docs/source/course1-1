Vescek Model::

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
        
        
现在是正常文字
