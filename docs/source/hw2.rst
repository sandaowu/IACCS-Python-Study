《复杂系统入门与实战(Python)》 作业2
=====

Python代码参考::


  import matplotlib.pyplot as plt
  import seaborn as sns

  # ------ 这是示例这个二维的格子世界，正式程序可以删掉 ------
  grids2D = np.zeros((20, 20), dtype='int8')
  grids2D[2][3] = 1
  grids2D[5][5] = 2
  grids2D[10][10] = 3
  grids2D[16][18] = 4

  # 这是画图的程序，将 grids2D 作为输入即可画图
  plt.subplots(1, figsize=(8,8), dpi=60)
  plt.clf()
  ax = plt.gca()
  sns.heatmap(grids2D, linewidths=0.1, vmin=-1, vmax=5, cmap='tab20c', cbar=False)
  ax.set_aspect('equal', adjustable='box')
  ax.set_xticks([])
  ax.set_yticks([])

  
  
  # ------ 这是做动画的函数，亦可参照第一次作业的动画函数 ------
  import matplotlib.animation
  
  fig, ax = plt.subplots(1, figsize=(8,8), dpi=60)
  ani = matplotlib.animation.FuncAnimation(fig, update, init_func=initStep, frames=Nstep)
  ani.save('evolve.mp4', writer='ffmpeg', fps=30)
