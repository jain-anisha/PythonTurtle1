import turtle

t = turtle.Turtle()
turtle.tracer(0,0) # turn off animation
t.hideturtle()
screen = turtle.Screen()
screen.screensize(2000, 1750) # increasing the window size so the entire drawing can be seen

#originalEpicycloid and drawPolygon is from Debayan's code on GC.
#originalEpicycloid was named main, and Debayan wrote it when he was introducing epicycloids

#I am drawing the illuminati with a spiral in the back

def drawPolygon(t, sides, size):
	# we need to return a list of vertices
	vertices = [None]*sides # vertices = []

	angle = 360.0/sides # play around with this
	for i in range(sides):
		vertices[i] = t.pos() # vertices.append(  t.pos()  )
		t.forward(size)
		t.right(angle)
	# loop ends

	return vertices 
	
#==================================================

def epicycloidAKAIris(start):
	# this code gets executed

	#==============================================
	# settings
	t.pensize(1)
	t.pencolor("red")
	turtle.bgcolor('light blue')

	t.penup()
	t.setpos(start)
	t.pendown()

	#==============================================
	# code!
	n = 100 # number of vertices or sides
	v = drawPolygon(t, n, 6) # 50-sided, with each side = 50 steps long

	used = [False]*n # just a table, saying that no vertex has been used yet

	# go through all the vertices (not starting from 0 - why??)0
	for current in range(1, n):

		# start from this vertex, making sure not to leave a trailing line
		t.penup()
		t.setposition( v[current] )
		t.pendown()

		# bounce around the polygon, stopping only when you hit a used vertex
		while used[current] == False:
			used[current] = True # this vertex is now used
			nextVertex = (current * 59)%n # using a different multiplier will change the shape!
			t.setposition( v[nextVertex] )
			current = nextVertex

		if 7 < current < 125:
			t.pencolor("magenta")
			t.pensize(1.75)
		else:
			t.pencolor("light green")
			t.pensize(1.5)
	return

def drawpupil():	#draws the pupil
	t.penup()
	t.setpos(0,-25)
	t.pendown()
	t.fillcolor('black')
	t.pensize(4)
	t.begin_fill()
	t.circle(50)
	t.end_fill()
	return

def drawEye():		#draws the eye using the epicycloid and pupil 'def'
	epicycloidAKAIris([-3, 120])
	drawpupil()
	return

# method to draw ellipse
def drawWhiteEye(r):
	
	turtle.penup()
	turtle.setpos(-140, -45)
	turtle.pendown()
	turtle.hideturtle()
	# rad --> radius of arc
	# the drawing of the oval is taken from stackoverflow at https://stackoverflow.com/a/50890109
	turtle.right(45)
	turtle.fillcolor('white')
	turtle.pensize(2)
	turtle.begin_fill()
	for loop in range(2):      # Draws 2 halves of ellipse
		turtle.circle(r,90)    # Long curved part
		turtle.circle(r/2,90)
	turtle.end_fill()
	return

# calling draw method

def purpleSpiral(x, penSize, color, angle):
	y = turtle.Turtle()
	y.hideturtle()
	y.speed(0)
	y.pensize(penSize)
	y.penup()
	y.setpos(135, 130)
	y.pendown()

	for i in range(x):
		y.forward(2*i)
		y.right(40)

		for i in range(15):
			y.pencolor('purple')
			y.forward(4*i)
			y.right(angle)
			if i > 5:
				y.pencolor(color)
	return

def drawTriangle(startPoint, triangleSide):
	k = turtle.Turtle()
	k.penup()
	k.setpos(startPoint)
	k.fillcolor('purple')
	k.begin_fill()
	k.pendown()
	k.right(60)
	k.forward(triangleSide)
	k.left(120)
	k.forward(2*triangleSide)
	k.left(120)
	k.forward(2*triangleSide)
	k.left(120)
	k.forward(triangleSide)
	k.end_fill()
	k.left(60)
	k.fillcolor('light green')
	k.begin_fill()
	for i in range(3):
		k.forward(triangleSide)
		k.left(120)
	k.end_fill()
	return

purpleSpiral(600, 2.5, 'light green', 25) 			# draw the spiral behind the drawing
drawTriangle([-350, -185], 695)						#draw triangles behind the eye
purpleSpiral(200, 1.75, 'magenta', 13.9) 			#draw the spiral in front of the drawing
drawWhiteEye(200)									#draw the white oval behind the iris

epicycloidAKAIris([-3, 120])
drawEye()

#==============================================
turtle.update()
turtle.done()
