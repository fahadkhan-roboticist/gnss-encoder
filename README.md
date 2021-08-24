# gnss-encoder

GNSS and wheel encoder will give us x, y and angle. I had an experience of sensor fusion from my Autonomy of Robot assignment, based on that I figured out. To solve the given task we can use EKF (extended Kalman Filter), we can also use Monte Carlo Localization algorithm and particle filter. I decided to start with EKF and compare this result with particle filter. 



Algorithm MCL (X_(t-1),u_t,z_t):	
	X_t= ∅ 
	For m = 1 to M:
		x_t^[m] =GNSS_update (u_t,x_(t-1)^[m]  )
		w_t^([m])=encoder_data (z_t,x_t^[m]  )
	end for
	For m=1 to M:
		Draw (x_t^[m]  )  from (X_t )  with probablity ∝ (w_t^[m]  )
		X_t=X_t+ x_t^[m] 
	end for
	return X_t
	
![image](https://user-images.githubusercontent.com/82445577/130588071-68aea8be-3cc9-46df-81cc-0614632fb2a7.png)

	
![image](https://user-images.githubusercontent.com/82445577/130587966-65490366-15b2-4858-86bb-78f00b57438e.png)
