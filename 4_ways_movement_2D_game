extends CharacterBody2D

const SPEED = 130.0

var gravity = ProjectSettings.get_setting("physics/2d/default_gravity")
@onready var animated_sprite = $AnimatedSprite2D


func _physics_process(delta):
	var velocity = Vector2()
	velocity = Vector2()

	if Input.is_action_pressed("move_right"):
		velocity.x += 1
		animated_sprite.flip_h = false

	elif Input.is_action_pressed("move_left"):
		velocity.x -= 1
		animated_sprite.flip_h = true

	elif Input.is_action_pressed("move_down"):
		velocity.y += 1

	elif Input.is_action_pressed("move_up"):
		velocity.y -= 1

	velocity = velocity.normalized() * SPEED
	move_and_collide(velocity * delta)

	if velocity != Vector2.ZERO:	
		animated_sprite.play("run")
		
	else:
		animated_sprite.play("idle")

