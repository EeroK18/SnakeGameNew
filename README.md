SnakeGameNew
============


import java.awt.Canvas;
import java.awt.Color;
import java.awt.Graphics;
import java.awt.Point;
import java.util.LinkedList;



	public class SnakeCanvas extends Canvas {
		
		private final int heightBox = 5;
		private final int widthBox = 5;
		private final int widthGrid = 30;
		private final int heightGrid = 30;
		private int direction = Direction.noDirection;
		
		private LinkedList<Point> snake;
		private Point food;
		
		public void draw(Graphics g)
		{
			drawGrid (g);
			drawSnake (g);
			drawFood (g);
			
			
		}
		
		public void drawGrid(Graphics g){
			// drawing the border rectangle
			g.drawRect(0,0, widthBox * widthGrid, heightBox*heightGrid);
			//drawing the vertical lines
			
			for (int y= widthBox; y <heightGrid * heightBox; y+=heightBox){
				
				g.drawLine(0, y, widthGrid*widthBox, y);
			}
			
			
			
		}
		
		public void drawSnake(Graphics g){
			
			g.setColor (Color.GREEN);
			for (Point p : snake){
			g.fillRect(p.x*widthBox, p.y*heightBox, widthBox, heightBox); // draws body of snake making it green
			}
			g.setColor(Color.BLACK); // background is black
			
		}
		
		public void drawFood(Graphics g)
		{
			g.setColor(Color.RED);
			g.fillOval(food.x*widthBox, food.y*heightBox, widthBox, heightBox);
			
		}
		
		public void Move(){
			Point head = snake.peekFirst();
			Point newPoint = head;
			switch (direction){
			
			case Direction.NORTH:
				newPoint = new Point(head.x, head.y - 1);
			break;
			
			case Direction.SOUTH:
				newPoint = new Point(head.x, head.y + 1);
			break;
			
			case Direction.WEST:
				newPoint = new Point(head.x-1, head.y);
			break;
			
			case Direction.EAST:
				newPoint = new Point(head.x+1, head.y);
			break;
			
			}
			
			snake.remove(snake.peekLast());
			
			if (newPoint.equals(food)){
				
			}
			else if(newPoint.x<0||newPoint.x>widthGrid ){
				
				
			}
			else if(newPoint.y<0||newPoint.y>heightGrid){
				
			}
			
			else if (snake.contains(newPoint)){
				
			}
			
			snake.push(newPoint);

		}

		
		
		
		
		
		
		
		
		
		
		
		public void Run(){
			
			
				
				
				
			}
			
		}
		

