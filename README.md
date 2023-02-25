<!-- MiniHawk-VTOL README.md - Enable Word wrap in your Text Viewer/Editor -->
# MiniHawk-VTOL <a name="head-brief"></a>

> - [Инструкции по сборке](https://github.com/StephenCarlson/MiniHawk-VTOL/tree/development#build-sequence-)
> - [Документация](https://github.com/StephenCarlson/MiniHawk-VTOL/tree/development/doc-Documentation)
> - [Аналогичная модель для RealFlight](https://github.com/sdpauck/MiniHawk-VTOL/sim-Convergence_Tilt_Tri_QuadPlane)
> - Видео [Сборка распечатанных деталей](https://www.youtube.com/watch?v=nICNlJhoEvw)
> - Видео [Взлёт - переход - полёт - переход - посадка](https://www.youtube.com/watch?v=mDxm1YLxNSA)
> - Плэйлист [Другие видео по теме](https://www.youtube.com/watch?v=4NjTIWN3P_c&list=PLEMjH2uELUcYI_DS1zthgjE4Su79LeA_G)
> - [Страница на hackaday.io](https://hackaday.io/project/175286-minihawk-vtol)
> - [Страница на rcgroups](https://www.rcgroups.com/forums/showthread.php?3986653-MiniHawk-VTOL-A-3D-Printed-Tricopter-Tilt-Rotor-Fixed-Wing-Plank)
> - [Сборки на RCGroups](https://www.rcgroups.com/forums/showthread.php?3750791-KatanaGuy-s-MiniHawk-VTOL)

# Table of Contents
1. [Metrics](#head-metrics)  
  1.1 [Профиль](#head-airfoil) 
2. [Компоненты](#build-components)  

4. [Flight Testing](#flight-brief)  
5. [3D Printing Guidelines](#3dprinting-brief)  
6. [ArduPlane](#arduplane-brief)  
  6.1 [R/C Controls Configuration](#arduplane-controlsconfig)  
  6.2 [Flight Controller Connections](#arduplane-connections)  
  6.3 [Parameters](#arduplane-parameters)  
  6.4 [Remarks](#arduplane-remarks)  
8. [License](#license-brief)  



## Metrics <a name="head-metrics"></a>
| Description              | Value                     |
|--------------------------|---------------------------|
| Wing Span                | 800mm                     |
| Wing Area                | 15.6dm^2                  |
| Aspect Ratio             | 4.1                       |
| Airfoil (Root and Tip)   | [MH45][1]                 |
| Length                   | 520mm                     |
| Rotor Spacing            | 315mm Circle              |
| Lipoly Battery           | 4s, 1300-1500mAh (~160g)  |
| Motors (front)           | 2207 or 2306 2300-2600kV  |
| Motor (rear)             | 2207 or 2306 ~2000kV      |
| Servos                   | HS-65HB/MG or eqv.        |
| Flight Controller (size) | 30.50mm to 16.0mm Grid    |
| Propellers (front)       | 5050 to ~5249             |
| Propeller (rear)         | 6030 to ~5249             |
| All-up Weight            | 1000g to ~1200g w/ PLA    |
## Профиль <a name="head-airfoil"></a>
[MH45 Airfoil by Martin Hepperle](https://www.mh-aerotools.de/airfoils/mh45koo.htm)  


## Компоненты <a name="build-components"></a>
| Кол.| Назване                                              | Примечание                                         |
|-----|------------------------------------------------------|----------------------------------------------------|
| 1   | Flight Controller (3 Motor, 4 Servo Outputs)         | Matek F405-WING or F765-WING                      |
| -   | Pitot Probe, GPS, Telem. Radios, FPV Cam+VTx, etc    | Additional Essential Avionics                      |
| 1   | UBEC for servo power if not built into Flight Ctrlr. | Castle Creations 10 Amp Adjustable BEC             |
| 1   | R/C Receiver, 8+ Channel, SBUS or PPM Output         |                                                    |
| 3   | ESC (4s, 40A or better)                              | EMAX Formula Series 32Bit 45A ESC                  |
| 2   | 2207 or 2306 ~2500KV BLDC Motor (Out.Dia. < 29mm)    | T-Motor VELOX V2 2207 2550Kv (Note 1)              |
| 1   | 2207 or 2306 ~2000KV BLDC Motor                      | T-Motor VELOX V2 2306 1950Kv (Note 2)              |
| 1   | 4s1300 Lipoly (60C or better)                        | RDQ 14.8V 4S 1300mAh 100C                          |
| 1   | XT60 Pigtail or equiv.                               |                                                    |
| 2   | HS-65HB Servo (or equiv.)                            | Elevon Servos, see (Note 3).                       |
| 2   | HS-5065MG Servo (or equiv.)                          | Motor Tilt Servos, see (Note 4).                   |
| 1   | Carbon Fiber Spar, Length<640mm, Out.Dia.<=6.5mm     | Used to strengthen the wings. Round or Square      |
| 6   | (opt) Du-Bro SKU#118 Small Nylon Hinge               | Elevon Reinforcement, see (Note 5).                |
| -   | M2 or M3 Mounting Hardware (Nuts, Bolts, Standoffs)  | For mounting Flight Controller, trays.             |
| 4   | 6-Inch Servo Extension Cable                         | (Note 6)                                           |
| 1   | Male-to-Male Servo Extension Cable                   | Flight Controller to Receiver PPM/SBUS connection. |
| 4   | 2-56 Link Clevis (Note 7)                            | Four (4) servo arm connections.                    |
| 2   | 2-56 Threaded Linkage Rod, Length>=52mm              | Elevon pushrods, L-bend at 45mm from threaded tip. |
| 2   | (opt) Du-Bro SKU#855 E/Z Links 0.72 (2-56) Clip      | For securing L-Bends, can replace with Z-bend.     |
| 2   | 1/16-inch 2-56 Ball Link and Coupler Pair            | Dubro #181 or Dubro #190, see (Note 8).            |
| 2   | 2-56 Fully-Threaded Rod, Length=70mm                 | End1=(Link 2-56 Clevis), End2=(2-56 Ball Coupler)  |
| 2   | 2-56 Smooth Rod, Length=40mm                         | (Note 9)                                           |
| 4   | (opt) 3mm Bolt or Shaft, Length=44mm                 | If you want to use ball bearings to the tilt arms. |
| 4   | (opt) 3x6x2.5mm Ball Bearing                         | Commonly known as MR63ZZ, for tilt arm supports.   |
| 2   | (opt) WS2812 5050 SMD (or equiv. Addressable LED)    | Soldered with magnet wire, mounted in wingtips.    |
| -   | M4 or M5 Prop Nuts                                   | Replace default prop nuts if needed                |
| 1   | 50xx Propeller, Clockwise Rotation                   | Left/Port-side Propeller, 5-inch                   |
| 1   | 50xx Propeller, Counterclockwise Rotation            | Right/Starboard-side Propeller, 5-inch             |
| 1   | 50xx or 60xx Propeller, Counterclockwise Rotation    | Tail Propeller, Dalprop Foldable F6 6048 Tri-blade |
| 1   | Velcro Battery Strap                                 |                                                    |
| 1   | (opt) Battery Voltage Monitor / Alarm Buzzer         | For Flight Controller if not included.             |

> Примечание 1: Передние двигатели должны быть не более 29 мм, способны создавать статическую тягу от 500 до 800 г и скорость тангажа ~ 20 м/с  с 5-дюймовым винтом.  
> Примечание 2: Хвостовой двигатель может иметь наружный диаметр 30 мм и более, способный создавать статическую тягу от 700 до 1000 г с 6-дюймовым винтом.  
> Примечание 3: Отсеки для сервоприводов предназначены для сервоприводов шириной до 26 мм, 17,5 мм от нижней части монтажных выступов до нижней части сервопривода, 32 мм от верхней части выходного вала до нижней части сервопривода, толщиной 12 мм. Подходит для большинства сервоприводов "Sub-Micro".  


# Рекомендации по печати деталей корпуса <a name="3dprinting-brief"></a>
| Parameter                 | Left and Right Wings           | Nose                    | Empennage               | Hatch/Lid               | Nacelles                  | Motor Tilt Mounts         |
|---------------------------|--------------------------------|-------------------------|-------------------------|-------------------------|---------------------------|---------------------------|
| LayerHeight               | 0.2mm                          | 0.2mm                   | 0.2mm                   | 0.2mm                   | 0.2mm                     | 0.2mm                     |
| WallThickness             | 0.4mm                          | 0.4mm                   | 0.4mm                   | 0.4mm                   | 0.8mm                     | 0.8mm                     |
| TopThickness              | 0.2mm                          | 0.2mm                   | 0.2mm                   | 0.2mm                   | 0.6mm                     | 0.6mm                     |
| BottomThickness           | 0.2mm                          | 0.2mm                   | 0.2mm                   | 0.2mm                   | 0.6mm                     | 0.6mm                     |
| TopBottomMainPattern      | Lines                          | Concentric              | Lines                   | Lines                   | Lines                     | Lines                     |
| InitialBottomLayerPattern | Concentric                     | Concentric              | Concentric              | Concentric              | Lines                     | Lines                     |
| FillGapsBetweenWalls      | Nowhere                        | Nowhere                 | Nowhere                 | Nowhere                 | Everywhere                | Everywhere                |
| Z-SeamAlignment           | UserSpecified (Note 1)         | SharpestCorner,HideSeam | SharpestCorner,HideSeam | SharpestCorner,HideSeam | SharpestCorner,ExposeSeam | SharpestCorner,ExposeSeam |
| InfillDensity             | 5.00%                          | 10.00%                  | 10.00%                  | 10.00%                  | 20.00%                    | 30.00%                    |
| InfillPattern             | Cubic                          | Cubic                   | Cubic                   | Cubic                   | Cubic                     | Cubic                     |
| InfillLineDirections      | 90deg                          | 0deg                    | 0deg (Note 2)           | 90deg                   | 0deg                      | 0deg                      |
| GenerateSupport           | Nowhere                        | Nowhere                 | Nowhere                 | Nowhere                 | Yes                       | Nowhere                   |
| SupportPlacement          |                                |                         |                         |                         | TouchingBuildPlate        |                           |
| SupportOverhangAngle      |                                |                         |                         |                         | 70deg                     |                           |
> Note 1: Forced to occur on trailing edge of wing.  
> Note 2: Is slightly offset in X-direction for best structure.  

# Настройки ArduPlane  <a name="arduplane-brief"></a>

## R/C Controller Configuration (Mode 2 Controller) <a name="arduplane-controlsconfig"></a>
| R/C Channel | Description         | 1000us         | 1500us     | 2000us                  | Notes                                                          |
|-------------|---------------------|----------------|------------|-------------------------|----------------------------------------------------------------|
| CH 1        | Roll                | Roll Left      | Centered   | Roll Right              |                                                                |
| CH 2        | Pitch               | Nose Up        | Neutral    | Nose Down               |                                                                |
| CH 3        | Throttle/Collective | Idle           | 50% Thrust | 100% Thrust             | Be careful switching between QSTABILIZE and QLOITER/QHOVER     |
| CH 4        | Rudder              | Yaw Left       | Neutral    | Yaw Right               |                                                                |
| CH 5        | Flight Mode Select  | FBWA           | QSTABILIZE | AUTO/RTL/AUTOTUNE       | 3-Position Switch, 2000us is formed by mixing a 2nd R/C switch |
| CH 6        | MANUAL Override     | Disabled       | ---        | MANUAL Mode ACTIVE!     | RC6_OPTION=51, useful for hand-launching into forward-flight   |
| CH 7        | Arming Switch       | Disabled       | ---        | ARMED!                  | RC7_OPTION=41, ArduPilot Arming/Disarming Switch               |
| CH 8        | Momentary Switch    | Disabled       | ---        | OSD, Inverted Mode, etc | OSD Screen Cycling, Inverted (RC8_OPTION=43), other misc uses  |

## ШИМ выходы на Matek F405-WING <a name="arduplane-connections"></a>
| Pin # | Control Endpoint    |
|-------|---------------------|
| S1    | Right Motor ESC     |
| S2    | Left Motor ESC      |
| S3    | NO CONNECTION (BEC) |
| S4    | Rear/Tail Motor ESC |
| S5    | Left Tilt Servo     |
| S6    | Right Tilt Servo    |
| S7    | Left Elevon Servo   |
| S8    | Right Elevon Servo  |

## Параметры ArduPlane <a name="arduplane-parameters"></a>
Параметры для mRo PixRacer Pro.  
Основные настройки должны быть применимы к любому используемому полетному контроллеру, например, к Matek F405-WING или аналогичному, но потребуется некоторая адаптация.
  
mRo PixRacer Pro: [ArduPlane_MiniHawk_mRo_PixRacerPro.param](/cfg-Config/ArduPlane_MiniHawk_mRo_PixRacerPro.param)
  
Некоторые важные параметры:
```
| Parameter,Value        | Notes                                                      |
| ---------------------- | ---------------------------------------------------------- |
| ARSPD_FBW_MAX,32       | Full-Throttle produces around 32 to 34 m/s sprint velocity |
| ARSPD_FBW_MIN,17       | Stall is near 15 m/s for a typical MiniHawk-VTOL           |
| ARSPD_RATIO,1.9936     | Make sure this is calibrated for your aircraft             |
| ARSPD_TUBE_ORDER,0     | While this can be automatic (3), manually set is better    |
| ARSPD_TYPE,1           | MS4525D0 Pressure Sensor, adjust as needed                 |
| ARSPD_USE,1            | Force the aircraft to use the pitot probe, no synthetic    |
| AUTOTUNE_LEVEL,7       | 7 or 8 works best for the MiniHawk-VTOL                    |
| EK2_ENABLE,0           | EKF2 is Disabled, in favor of EKF3                         |
| EK3_ENABLE,1           | EKF3 was used for most flight testing of the design        |
| FLTMODE_CH,5           | Flight Mode Channel                                        |
| FLTMODE1,5             | FBWA, 3-position switch "Down" detent                      |
| FLTMODE2,19            | QLOITER, 3-position switch "Middle" detent                 |
| FLTMODE3,17            | QSTABILIZE, 3-position switch "Up" detent                  |
| FLTMODE4,17            |                                                            |
| FLTMODE5,17            |                                                            |
| FLTMODE6,10            | AUTO, 2nd R/C switch that overrides the 3-position switch  |
| FS_LONG_ACTN,1         | Failsafe Settings used in development                      |
| FS_LONG_TIMEOUT,3      |                                                            |
| FS_SHORT_ACTN,1        |                                                            |
| FS_SHORT_TIMEOUT,1     |                                                            |
| KFF_RDDRMIX,0          | Remove any possible rudder mixing                          |
| LIM_PITCH_MAX,2000     | Pitch and Roll Angle Limits                                |
| LIM_PITCH_MIN,-2500    |                                                            |
| LIM_ROLL_CD,5500       |                                                            |
| MIXING_GAIN,0.5        | Elevon Stick Mixing, value here should be default          |
| NAVL1_PERIOD,11        | More aggressive navigation is possible, 11 to 14 tested    |
| PTCH_RATE_D,0          | Pitch PIDs, these values are mild, AUTOTUNE will increase  |
| PTCH_RATE_FF,0.345     |                                                            |
| PTCH_RATE_FLTD,4       |                                                            |
| PTCH_RATE_FLTE,7       |                                                            |
| PTCH_RATE_FLTT,1.5     |                                                            |
| PTCH_RATE_I,0.15       |                                                            |
| PTCH_RATE_IMAX,0.666   |                                                            |
| PTCH_RATE_P,0.04       |                                                            |
| PTCH_RATE_SMAX,150     |                                                            |
| PTCH2SRV_RLL,1         |                                                            |
| PTCH2SRV_RMAX_DN,90    |                                                            |
| PTCH2SRV_RMAX_UP,90    |                                                            |
| PTCH2SRV_TCONST,0.4    |                                                            |
| Q_A_ACCEL_P_MAX,110000 | VTOL R/P/Y Angular accelerations used in development       |
| Q_A_ACCEL_R_MAX,110000 |                                                            |
| Q_A_ACCEL_Y_MAX,27000  |                                                            |
| Q_A_RAT_PIT_D,0.0005   | VTOL Pitch PIDs                                            |
| Q_A_RAT_PIT_FF,0       |                                                            |
| Q_A_RAT_PIT_FLTD,15    |                                                            |
| Q_A_RAT_PIT_FLTE,0     |                                                            |
| Q_A_RAT_PIT_FLTT,20    |                                                            |
| Q_A_RAT_PIT_I,0.15     |                                                            |
| Q_A_RAT_PIT_IMAX,0.5   |                                                            |
| Q_A_RAT_PIT_P,0.15     |                                                            |
| Q_A_RAT_PIT_SMAX,0     |                                                            |
| Q_A_RAT_RLL_D,0.003    | VTOL Roll PIDs                                             |
| Q_A_RAT_RLL_FF,0       |                                                            |
| Q_A_RAT_RLL_FLTD,15    |                                                            |
| Q_A_RAT_RLL_FLTE,0     |                                                            |
| Q_A_RAT_RLL_FLTT,20    |                                                            |
| Q_A_RAT_RLL_I,0.25     |                                                            |
| Q_A_RAT_RLL_IMAX,0.5   |                                                            |
| Q_A_RAT_RLL_P,0.45     |                                                            |
| Q_A_RAT_RLL_SMAX,0     |                                                            |
| Q_A_RAT_YAW_D,0.02     | VTOL Yaw PIDs                                              |
| Q_A_RAT_YAW_FF,0.1     |                                                            |
| Q_A_RAT_YAW_FLTD,0     |                                                            |
| Q_A_RAT_YAW_FLTE,10    |                                                            |
| Q_A_RAT_YAW_FLTT,20    |                                                            |
| Q_A_RAT_YAW_I,0.1      |                                                            |
| Q_A_RAT_YAW_IMAX,0.5   |                                                            |
| Q_A_RAT_YAW_P,0.6      |                                                            |
| Q_A_RAT_YAW_SMAX,0     |                                                            |
| Q_ANGLE_MAX,3000       | VTOL Pitch and Roll Angle Limits                           |
| Q_ASSIST_ALT,0         | Disable VTOL Assist where possible                         |
| Q_ASSIST_ANGLE,0       |                                                            |
| Q_ASSIST_DELAY,0.5     |                                                            |
| Q_ASSIST_SPEED,0       |                                                            |
| Q_AUTOTUNE_AGGR,0.1    | VTOL Autotune settings used in development                 |
| Q_AUTOTUNE_AXES,2      |                                                            |
| Q_AUTOTUNE_MIN_D,0.001 |                                                            |
| Q_ENABLE,1             | VTOL obviously is enabled for the MiniHawk-VTOL            |
| Q_FRAME_CLASS,7        | Tricopter Configuration                                    |
| Q_FW_LND_APR_RAD,85    | 85 meters for Fixed-wing to VTOL threshold                 |
| Q_M_HOVER_LEARN,2      | Hover throttle setpoint learning                           |
| Q_M_PWM_TYPE,4         | DShot 150 is sufficient and noise-resistant                |
| Q_M_SPIN_ARM,0.05      | 5% Throttle when armed                                     |
| Q_M_SPIN_MAX,1         | 100% Throttle max ESC RPM command                          |
| Q_M_SPIN_MIN,0.1       | 10% Throttle for lowest ESC RPM                            |
| Q_M_SPOOL_TIME,0.5     | 500ms spool time                                           |
| Q_M_THST_EXPO,0.25     | Throttle Expo                                              |
| Q_M_YAW_HEADROOM,50    | 50us Yaw Headroom                                          |
| Q_M_YAW_SV_ANGLE,12    | "12" Degrees for Yaw lean angle                            |
| Q_OPTIONS,1056         | Allow yaw actuation when disarmed, QRTL behavior           |
| Q_RC_SPEED,490         | 490 Hz Motor Updates                                       |
| Q_RTL_ALT,40           | RTL Behaviors in VTOL                                      |
| Q_RTL_MODE,1           |                                                            |
| Q_TILT_MASK,3          | Which motors are being tilted                              |
| Q_TILT_MAX,55          | Transition angle while AirspeedWait is active              |
| Q_TILT_RATE_DN,15      | Tilt Up/Down rates                                         |
| Q_TILT_RATE_UP,75      |                                                            |
| Q_TILT_TYPE,2          | Vectored Yaw Tilt Type                                     |
| Q_TILT_YAW_ANGLE,14    | "14" degrees VTOL hover position                           |
| Q_TRANS_FAIL,0         | Transition Timeout is disabled                             |
| Q_TRANSITION_MS,1000   | Post-transition wait period                                |
| Q_TRIM_PITCH,9         | Pitch offset between forward-flight and hover stance       |
| Q_WVANE_GAIN,0.4       | 0.4 is a good value for this design                        |
| RC7_OPTION,41          | Arming Switch, will disable motors if in flight/hover!     |
| RCMAP_PITCH,2          | Roll/Pitch/Throttle/Yaw (AETR) controls ordering           |
| RCMAP_ROLL,1           |                                                            |
| RCMAP_THROTTLE,3       |                                                            |
| RCMAP_YAW,4            |                                                            |
| RLL_RATE_D,0           | Roll PIDs, these values are mild, AUTOTUNE will increase   |
| RLL_RATE_FF,0.345      |                                                            |
| RLL_RATE_FLTD,4        |                                                            |
| RLL_RATE_FLTE,7        |                                                            |
| RLL_RATE_FLTT,3        |                                                            |
| RLL_RATE_I,0.15        |                                                            |
| RLL_RATE_IMAX,0.666    |                                                            |
| RLL_RATE_P,0.08        |                                                            |
| RLL_RATE_SMAX,150      |                                                            |
| RLL2SRV_RMAX,90        |                                                            |
| RLL2SRV_TCONST,0.4     |                                                            |
| RTL_AUTOLAND,2         | Fixed-wing to VTOL landing behavior in RTL                 |
| RUDD_DT_GAIN,3         | Very mild differential thrust mixing on forward motors     |
| SCALING_SPEED,15       | 15 m/s should be default                                   |
| SCHED_LOOP_RATE,300    | 300 Hz was used in development                             |
| SERVO1_FUNCTION,33     | Right BLDC Motor                                           |
| SERVO2_FUNCTION,34     | Left BLCD Motor                                            |
| SERVO3_FUNCTION,0      | No Connection, 5V BEC connected here for mRo PixRacer Pro  |
| SERVO4_FUNCTION,36     | Rear BLCD Motor                                            |
| SERVO5_FUNCTION,75     | Left Tilt Servo                                            |
| SERVO5_MAX,1800        | MAX and MIN values are hand calibrated, close to 1920/1080 |
| SERVO5_MIN,1200        | Values of 1200/1800 here to prevent damage on new builds   |
| SERVO5_REVERSED,0      | Left Tilt is normal rotation direction                     |
| SERVO6_FUNCTION,76     | Right Tilt Servo                                           |
| SERVO6_MAX,1800        |                                                            |
| SERVO6_MIN,1200        |                                                            |
| SERVO6_REVERSED,1      | Right Tilt is reversed rotation direction                  |
| SERVO7_FUNCTION,77     | Left Elevon Servo                                          |
| SERVO7_REVERSED,1      | Left Elevon is reverse rotation direction                  |
| SERVO8_FUNCTION,78     | Right Elevon Servo                                         |
| SERVO8_REVERSED,0      | Right Elevon is normal rotation direction                  |
| STAB_PITCH_DOWN,2      | 2 should be default, pitch behavior on zero-throttle       |
| STALL_PREVENTION,0     | May be enabled, was disabled for development               |
| STICK_MIXING,1         | How pilot inputs are fused in autonomous modes             |
| TECS_PTCH_FF_V0,19     | 19 m/s cruise                                              |
| TRIM_ARSPD_CM,1900     | 19 m/s cruise                                              |
| TRIM_PITCH_CD,350      | Offset between level-flight pitch angle and tray angle     |
| TRIM_THROTTLE,55       | Typical 19 m/s cruise throttle                             |
| WP_LOITER_RAD,60       | 60 meter radius for loiter typical                         |
| WP_RADIUS,40           | 40 meter waypoint radius typical                           |
```

  
## Примечания: <a name="arduplane-remarks"></a>
Тестировалось на ArduPlane v4.1.0 and v4.2.0dev.  
  
At this firmware version, there are some aspects of how VTOL flight behaviors are handled which are somewhat counter-intuitive. The most annoying of these is that for both piloted and autonomous flying, there is no direct control of the VTOL flight state. Instead of being able to directly command the Forward-Flight condition, the VTOL state-machine requires an airspeed estimate (either synthetic or measured from a pitot probe) to drive the forward VTOL transition to fixed-wing flight. This makes the human pilot merely a voting member in the transition process, with accumulated airspeed determining when the tilting rotors are allowed to fully tilt forward and the rear motor to halt. The developers' mentality treats the hover condition as the default fallback, and any failure to accumulate airspeed in a certain amount of time will have the process revert to hover as a failsafe via `Q_TRANS_FAIL`. If this transition failure timeout is disabled, the AirspeedWait state will persist and the vehicle will fly in a half-way blend between tricopter and fixed-wing flight indefinitely. For a vehicle design such the MiniHawk-VTOL, over-powered and very fast, it would make more sense for a timeout to result in forcing forward-flight rather than to place the vehicle in this blended behavior, or if using the transition failure timer, to place the vehicle into hover with limited battery at extreme range and altitude, but that is a pull request for another day. And thus, for the current firmware state, it is necessary to be aware of this behavior and to know why it gets stuck in the blended mode.
  
Другим последствием поведения вертикального взлета и посадки вперед является то, что при снятии с охраны, даже если выбор режима полета вперед (например, FBWA) приведет к наклону винтов в положение вперед, после постановки на охрану машина немедленно перейдет в состояние AirspeedWait. при этом передние роторы наклоняются вверх, а задний ротор вращается вверх. Настройка дроссельной заслонки, по-видимому, определяет сочетание между зависанием и ожиданием скорости полета вперед, но лучшее решение, если вы пытаетесь запустить самолет вручную, как традиционный неподвижный крыло, — это «натолкнуться» на РУЧНОЙ режим на мгновение. Это вынуждает конечный автомат вертикального взлета и посадки выйти из состояния AirspeedWait и позволяет вам активировать режим FWBA и оставить передние роторы в переднем положении, а также насладиться стабилизацией и выравниванием элевонов при ручном запуске. Просто не забудьте переключиться из РУЧНОГО режима обратно в FBWA, если только вы не собираетесь полностью РУЧНОЙ ручной запуск без стабилизации или выравнивания.
  
Переходы от горизонтального полета к зависанию, как правило, плавные, когда им управляет человек, но в автономных режимах существует известная проблема, при которой аппарат наклоняется носом, а затем резко подтягивается при переходе в зависание. Это может быть опасно для аппарата, если отрицательная сила ускорения или внезапный рывок вызовут разделение деталей. Проблема, скорее всего, в параметрах настройки TECS или в прошивке 4.1 или 4.2
  
  
  
  
  
  

  
# License <a name="license-brief"></a>
This work is licensed under the [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-nc-sa/4.0/)  
The Ardupilot and Betaflight  is licensed under the GPL-3.0.  
[MiniHawk VTOL - Design, Documentation, Images and all other Artwork; by Steve Carlson](https://github.com/StephenCarlson/MiniHawk-VTOL)  
