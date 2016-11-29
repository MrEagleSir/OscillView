
[Rainmeter]
Update=1
SkinWidth=(1000)
SkinHeight=(1000)

[Metadata]
Author=MrEagleSir
NameOscillView
Version=1

[Variables]
;Size of the skin
Size=100

;Dot Size
Dotsize=5

;Color of the Dots
DotColor=255,255,255,255

;Audio
FFTSize=1524
FFTAttack=0
FFTDecay=0

;Sensitivity setting
Senc=100



A1=(500+([MeasureBand0])*500)
A2=(500-([MeasureBand1])*500)

;==============================================================

[MeasureAudio]
Measure=Plugin
Plugin=AudioLevel
Port=Output
FFTSize=#FFTSize#
FFTAttack=#FFTAttack#
FFTDecay=#FFTDecay#
Sensitivity=#Senc#


[MeasureBand0]
Measure=Plugin
Plugin=AudioLevel
Parent=MeasureAudio
Type=FFT
Channel=R


[MeasureBand1]
Measure=Plugin
Plugin=AudioLevel
Parent=MeasureAudio
Type=FFT
Channel=L

;=====================================================

[MeterA1Block]
Meter=Shape
Shape=Ellipse #A1#,#A2#,#Dotsize#
Color=Dotcolor
Solid=1
AntiAlias=1
DynamicVariables=1




