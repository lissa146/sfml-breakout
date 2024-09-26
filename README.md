# sfml-breakout
#include <SFML/Graphics.hpp>

class Ball {
private:
	sf::CircleShape shape;
	float radius;
	float xpos;
	float ypos;
	float xposvelocity;
	float yposvelocity;

public:
	Ball(float radius, float x, float y, float xvel, float yvel) {
		shape.setRadius(radius);
		xpos = x;
		ypos = y;
		xposvelocity = xvel;
		yposvelocity = yvel;

		shape.setPosition(xpos, ypos);
		shape.setFillColor(sf::Color::White);
	}
	void draw(sf::RenderWindow& window) {
		window.draw(shape);
	}

	//void move(float windowWidth, float windowHight) {
		//xpos += xvel;

		//if (xpos <= 0 || xpos + radius * 2 >= windowWidth) {
			//xvel = -xvel;
		//}
	//}

	//bool jayCollsion(Jay& jay) {
		//if (!jay.isDead() &&
			//xpos + radius > jay.getX() &&
			//xpos + radius < jay.getX() + jay.getWidth() &&
			//ypos + radius > jay.getY() &&
			//ypos + radius > jay.getY() + jay.getHeight()) {
			//jay.killJay();
			//return true;

		//}
		//return false;
	//}
};

class Jay {
private:
	float width;
	float height;
	float xpos;
	float ypos;
	bool dead;
	sf::RectangleShape shape;

public:
	Jay(float x, float y, float w, float h) {
		xpos = x;
		ypos = y;
		width = w;
		height = h;
		dead = false;

		shape.setSize(sf::Vector2f(width, height));
		shape.setPosition(xpos, ypos);
		shape.setFillColor(sf::Color::Red);
	}
	void draw(sf::RenderWindow& window) {
		if (!dead) {
			window.draw(shape);
		}
	}

	void killJay() {
		dead = true;
		shape.setFillColor(sf::Color::Transparent);
	}
	bool chechCollision(float ballX, float ballY, float ballRadius) {
		if (!dead &&
			ballX + ballRadius > xpos && ballX - ballRadius < xpos + width &&
			ballY + ballRadius > ypos && ballY - ballRadius < ypos + height) {
			killJay();
			return true;
		}
		return false;
	}
};

int main() {
	sf::RenderWindow window(sf::VideoMode(800, 600), "Jayout game");

	Jay jay1(100, 100, 50, 20);
	Jay jay2(160, 100, 50, 20);
	Jay jay3(220, 100, 50, 20);
	Jay jay4(280, 100, 50, 20);
	Jay jay5(340, 100, 50, 20);
	Jay jay6(400, 100, 50, 20);
	Jay jay7(460, 100, 50, 20);
	Jay jay8(520, 100, 50, 20);
	Jay jay9(580, 100, 50, 20);
	Jay jay10(640, 100, 50, 20);
	Jay jay11(700, 100, 50, 20);
	
	Jay jay12(100, 130, 50, 20);
	Jay jay13(160, 130, 50, 20);
	Jay jay14(220, 130, 50, 20);
	Jay jay15(280, 130, 50, 20);
	Jay jay16(340, 130, 50, 20);
	Jay jay17(400, 130, 50, 20);
	Jay jay18(460, 130, 50, 20);
	Jay jay19(520, 130, 50, 20);
	Jay jay20(580, 130, 50, 20);
	Jay jay21(640, 130, 50, 20);
	Jay jay22(700, 130, 50, 20);
	
	Jay jay23(100, 160, 50, 20);
	Jay jay24(160, 160, 50, 20);
	Jay jay25(220, 160, 50, 20);
	Jay jay26(280, 160, 50, 20);
	Jay jay27(340, 160, 50, 20);
	Jay jay28(400, 160, 50, 20);
	Jay jay29(460, 160, 50, 20);
	Jay jay30(520, 160, 50, 20);
	Jay jay31(580, 160, 50, 20);
	Jay jay32(640, 160, 50, 20);
	Jay jay33(700, 160, 50, 20);
	
	while (window.isOpen()) {
		sf::Event event;
		while (window.pollEvent(event)) {
			if (event.type == sf::Event::Closed)
				window.close();
		}


		jay1.draw(window);
		jay2.draw(window);
		jay3.draw(window);
		jay4.draw(window);
		jay5.draw(window);
		jay6.draw(window);
		jay7.draw(window);
		jay8.draw(window);
		jay9.draw(window);
		jay10.draw(window);
		jay11.draw(window);
		jay12.draw(window);
		jay13.draw(window);
		jay14.draw(window);
		jay15.draw(window);
		jay16.draw(window);
		jay17.draw(window);
		jay18.draw(window);
		jay19.draw(window);
		jay20.draw(window);
		jay21.draw(window);
		jay22.draw(window);
		jay23.draw(window);
		jay24.draw(window);
		jay25.draw(window);
		jay26.draw(window);
		jay27.draw(window);
		jay28.draw(window);
		jay29.draw(window);
		jay30.draw(window);
		jay31.draw(window);
		jay32.draw(window);
		jay33.draw(window);



		window.display();
	}
}
