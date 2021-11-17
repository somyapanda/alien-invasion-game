# Project - 1
## Alien Invasion - A ship That Fires Bullets

### Overview:
In Alien Invasion, the player controls a rocket ship that appears at the bottom center of the screen. The player can move the ship right and left using the arrow keys and shoot bullets using the spacebar. When the game begins, a fleet of aliens fills the sky and moves across and down the screen. The player shoots and destroys the aliens. If the player shoots all the aliens, a new fleet appears that moves faster than the previous fleet. If any alien hits the player's ship or reaches the bottom of the screen, the player loses a ship. If the player loses three ships, the game ends.

**Phase - 1**
    - Make a ship that can move right and left and fires bullets when the player presses the spacebar
    - Create the aliens and refine the gameplay

    **Steps to build ships:**
        - Install Pygame
        - Create a Pygame window and respond to user input
            - AlienInvasion starts as a class called AlienInvasion. 
            - In the __init__() method, the pygame.init() fuction initializes the background setting 
                that pygame needs to work properly.
            - pygame.display.set_mode() to create a display window on which we'll draw the game's graphical elements.
              The arguments (1200, 800) is a tuple that defines the dimension(width, height) of the game window.
            - Assign the above object to self.screen, so it will be available to all methods in the class. 
              It is called a surface. A surface in pygame is a part of the screen where a game element 
              can be displayed.
            - The surface returned by display.set_mode() represents the entire game window.
            - The game is controlled by run_game() method. This method contains a while loop that runs continually.
              The while loop contains an event loop and code that manages screen updates. An event is an action 
              that the user performs while playing the game, such as pressing a key or moving the mouse. To make
              our program respond to events we write this event loop to listen for events and perform appropriate 
              tasks depending on the kinds of events that occur. The for loop is an event loop.
            - The pygame.event.get() function returns a list of events that have taken place since tha last time this
              function was called. Any keybaoard or mouse event will cause this for loop to run.
            - Inside the loop, a series of if statements to detect and respond to specific events.
            - The call to pygame.display.flip() tells pygame to make the most recently drawn screen visible. The flip() 
              function continually updates the display to show the new positions of game elements and hides the old ones,
              creating the illusion of smooth movement.
            - Create an instance of the game, and then call run_game().
        - Set the background color
            - Colors in pygame are specified as RGB colors: a mix of red, green and blue. Each color value can range
              from 0 to 255. The color value (255, 0, 0) is red, (0,255, 0) is green and (0, 0, 255) is blue.
            - We choose (230, 230, 230) mixes all three colors and produces a light gray background color and we
              assign this color to self.bg_color.
            - We fill the screen with the background color using the fill() method, which acts on a surface and 
              takes only one argument: a color.
        - Create a setting class
            - Create a module called settings that contains a class called setting that allow 
               us to work with just one setting object any time we need to access an individual 
               setting. It makes easier to modify the game's apperance and behavior.
            - Create a file called setting.py.
            - To make an instance of 'Settings' in the project and use it to access the settings, we 
               do the followings:
                   - Import Settings into the main program file. 
                   - Create an instance of Settings and assign it to self.settings, after making the 
                     call to pygame.init().
                   - Use self.settings to access the background color.
        - Create a ship class
            - Save the ship image file as ship.bmp in the images folder.
            - To display the image of the ship on screen, we will create a new ship module 
              that contain the class ship.
            - Class manage the behavior of the player's ship.
            - Import the pygame module before defining the class.
            - The __init__() method of Ship takes two parameters:
                    - self reference
                    - a reference to the current instance of the 'AlienInvasion' class(this
                      will give Ship access to all the game resources defined in AlienInvasion).
            - Assign the screen to an attribute of Ship, so we can access it easily in all the 
              methods in this class.
            - In pygame, all the elements treated as rectangles(rects) because rectangles are simple
              geometric shapes.
            - Access the screen's rect attribute using the get_rect() method and assign it 
              to self.screen_rect. This allow us to place the ship in the correct location on the 
              screen.
            - Load the image by calling pygame.image.load() and give it the location of our 
              ship and assign it to self.image
            - When the image is loaded, we call get_rect() to access the ship surface's rect 
              attribute so we can later use it to place the ship.
            - We position the Ship at the bottom of the screen.
            - Blitme() method draws the image to the screen at the position specified by 
               self.rect.
        - Draw the Ship to the screen
            - Let's update alien_invasion.py so it creates a ship and calls the ship's blitme()
              method.
            - Import Ship and then make an instance of Ship after the screen has been created.
            - The call to Ship() requires one argument, an instance of AlienInvasion. The 
              self argument here refers to the current instance of AlienInvasion. This is the 
              parameter that gives Ship access to the game's resources such as the screen 
              object. 
            - Assign the Ship instance to self.ship
            - Draw the ship on the screen by calling ship.blitme(), so the ship appears on the
              bottom of the background.
            - Run the alien_invasion.py and see the ship at the bottom center.
            