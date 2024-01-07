# GoogleInterviewRiddle
# I wrote the problem in c# and printed it in the console application
# Math solution link 

[https://www.quora.com/How-Three-brothers-A-B-C-want-to-travel-300-km-They-have-a-bike-which-goes-in-uniform-velocity-60-km-h-which-can-carry-2-members-in-a-time-Each-brother-can-walk-15-km-h-how-they-can-reach-the-final-point-with
Three brothers A, B, C want to travel 300 km. They have a bike which goes in uniform velocity 60 km/h which can carry 2 members in a time. Each brother can walk 15 km/h how they can reach the final point with minimum time?]

My approach using simple algebra assumes that there be 4 states :-

Time =00; A,B,C are at point x, planning to reach point y. A starts walking, with Velocity of walking = Vw and B,C start on the bike, with Velocity of Bike = Vb.

Time =T1; B returns towards x to fetch A … A, C are walking towards y

Time =T2; A,B on bike start towards y, C is walking towards y.

Time =T3; A,B,C reach together at the destination y.

So the equation at T2, when A, B are together …

Position of A = Vw * T2

Position of B = Vb * T1 - Vb * ( T2 - T1 )

=> Vw * T2 = 2* Vb * T1 - Vb * T2

=> T1 = T2 * ( Vb + Vw ) / ( 2* Vb ) … … …. (1)

At T3, When A, B, C are together at destination y …

Position of A = Total Distance = Vw * T2 + Vb * ( T3 - T2 ) … … (2)

Position of B = Total Distance = Vb * T1 - Vb * ( T2 - T1 ) + Vb * ( T3 - T2 ) … (3)

Position of C = Total Distance = Vb * T1 + Vw * ( T3 - T1 ) … … (4)

Now Solving (4) and (2) … we get T3 = T1 + T2 … … (5)

Now Solving (1) and (5) … we get T2 = T3 * ( 2 * Vb )/( 3 * Vb + Vw ) … (6)

So …. by (5) … … T1 = T3 - T2

=> T1 = T3 - T3 * ( 2 * Vb )/( 3 * Vb + Vw )

=> T1 = T3 * ( Vb + Vw )/( 3 * Vb + Vw ) … (7)

Substituting (6) and (7) in (4) …

Total Distance = Vb * T1 + Vw * ( T2 )

=> Total Distance = Vb * T3 * ( Vb + Vw )/( 3 * Vb + Vw ) + Vw * T3 * ( 2 * Vb )/( 3 * Vb + Vw )

Now putting in the values

300 = T3 * 60 * ( 60+ 15 )/ (3*60 + 15) + T3 * 15 * 2* 60 / (3 * 60 + 15)

=> 300 = T3 * ( 60 * 75 / 195 + 30 * 60 / 195 )

=> T3 = 300 * 195 / (105 * 60)

=> T3 = 9.2857 hours is the total time.
