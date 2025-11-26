<h1>DQN Vs Double DQN</h1>
<section>
    <h2><strong>Project Overview</strong></h2>
    <p>
        This is the project repo for my CSCI 166 final project where I will be testing DQN and Double DQN. 
        This is done with the goal of seeing differences in the models and their uses.
    </p>
</section>

<section>
  <h2><strong>Hyperparameter & Tuning Tables</strong></h2>
  <p>Below is the catelog of each experiment done in this project.</p>
  
  <section>

  |   Version |   Mean Reward Bound |   Gamma |   Batch Size |   Replay Size |   Learning Rate |   Sync Target Frames |   Replay Start Size |   Save Epsilon |   Epsilon Decay Last Frame |   Epsilon Start |   Epsilon Final | Notes                                                                            |
  |:---------:|:-------------------:|-------:|-------------:|--------------:|----------------:|---------------------:|--------------------:|---------------:|---------------------------:|----------------:|----------------:|:--------------------------------------------------------------------------------|
  |         0 |                  19 |    0.99 |           32 |         10000 |          0.0001 |                 1000 |               10000 |            0.5 |                     150000 |               1 |           0.01  | Baseline run                                                                    |
  |         1 |                  19 |    0.99 |           64 |         10000 |          0.0001 |                 1000 |               10000 |            0.5 |                     150000 |               1 |           0.01  | Increase stability, try to help GPU                                             |
  |         2 |                  19 |    0.99 |           32 |         10000 |          0.0002 |                 1000 |               10000 |            0.5 |                     150000 |               1 |           0.01  | Increased Learning rate to encourage more aggressive learning                   |
  |         3 |                  19 |    0.99 |           32 |         10000 |          7e-05  |                 1000 |               10000 |            0.5 |                     150000 |               1 |           0.01  | Decreased Learning rate to encourage more stabilized learning                   |
  |         4 |                  19 |    0.97 |           32 |         10000 |          0.0001 |                 1000 |               10000 |            0.5 |                     150000 |               1 |           0.01  | Decreased gamma to prioritize more immediate rewards                            |
  |         5 |                  19 |    0.99 |           32 |         10000 |          0.0001 |                  500 |               10000 |            0.5 |                     150000 |               1 |           0.01  | Decreased sync target frames to encourage more frequent updates                 |
  |         6 |                  19 |    0.99 |           32 |         10000 |          0.0001 |                 1500 |               10000 |            0.5 |                     150000 |               1 |           0.01  | Increased sync target frames to encourage less frequent and more stable updates |
  |         7 |                  19 |    0.99 |           32 |         10000 |          0.0001 |                 1000 |               10000 |            0.5 |                     150000 |               1 |           0.005 | Decrease epsilon final to make agent greedier and less random                   |
  |         8 |                  19 |    0.99 |           32 |         10000 |          0.0001 |                 1000 |               10000 |            0.5 |                     150000 |               1 |           0.02  | Increase epsilon final to make agent less greedy and more random                |

  </section>
</section>

<section>
  <h2><strong>Videos</strong></h2>
  <h3>Baseline DQN:</h3>
  <p>Below is the baseline run of the single-DQN model variant.</p>

  <blockquote>

  | Environment | Model        | Training Stage   | Video                                                                                                  | Config Index |
  |-------------|--------------|------------------|--------------------------------------------------------------------------------------------------------|--------------|
  | Pong        | DQN          | Early (Random)   | <video width="240" controls><source src="videos/Pong/DQN/Initial_Baseline.mp4" type="video/mp4" /></video> | 0 |
  | Pong        | DQN          | Final (Trained)  | <video width="240" controls><source src="videos/Pong/DQN/Final_Baseline.mp4" type="video/mp4" /></video>               | 0 |
  | Breakout    | DQN          | Early (Random)   | <video width="240" controls><source src="videos/Breakout/DQN/ALE_Breakout-v5-first-0-20251125-1353.mp4" type="video/mp4" /></video>           | 0 |
  | Breakout    | DQN          | Final (Trained)  | <video width="240" controls><source src="videos/Breakout/DQN/ALE_Breakout-v5-final-20251125-1433.mp4" type="video/mp4" /></video>           | 0 |

  </blockquote>
    
  <h3>Baseline Double DQN</h3>
  <p>Below is the baseline run of the double-DQN model variant.</p>

  <blockquote>

  | Environment | Model        | Training Stage   | Video                                                                                                  | Config Index |
  |-------------|--------------|------------------|--------------------------------------------------------------------------------------------------------|--------------|
  | Pong        | Double DQN          | Early (Random)   | <video width="240" controls><source src="videos/Pong/DQN/Initial_Baseline.mp4" type="video/mp4" /></video> | 0 |
  | Pong        | Double DQN          | Final (Trained)  | <video width="240" controls><source src="videos/Pong/DQN/Final_Baseline.mp4" type="video/mp4" /></video>               | 0 |
  | Breakout    | Double DQN          | Early (Random)   | <video width="240" controls><source src="videos/Breakout/DQN/ALE_Breakout-v5-first-0-20251125-1353.mp4" type="video/mp4" /></video>           | 0 |
  | Breakout    | Double DQN          | Final (Trained)  | <video width="240" controls><source src="videos/Breakout/DQN/ALE_Breakout-v5-final-20251125-1433.mp4" type="video/mp4" /></video>           | 0 |

  </blockquote>
</section>

<h2>
  <a href="https://github.com/everestso/summer25/blob/main/c166f25_02b_dqn_pong.ipynb">
    Starter Code
    <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
  </a>
</h2>
