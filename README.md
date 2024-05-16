Im just messing around with the code of the Legacy4J mod


Important lines to remember
line 83 of LocalPlayerMixin found somewhere in common
setDeltaMovement(getDeltaMovement().add(0, -Math.sin(Math.toRadians(getXRot())) * input.forwardImpulse * getFlyingSpeed(), 0));

By changeing this line to muiltiply before the last comma i can modify how fast the charicter goes when flying up or down in this case it is multiplyed by 2
in theory multiplying it by 1 will change nothing.
I could probobly use this to make a setting in the settings menu of the game to modify how fast i want the charicter to move up and down
setDeltaMovement(getDeltaMovement().add(0, -Math.sin(Math.toRadians(getXRot())) * input.forwardImpulse * getFlyingSpeed() * 2, 0));


---


LivingEntityMixin controls the flight speed horasontally and the inb game friction








---

changing some of the lines of code here caused an unintended side effect of giving the player the abiblity to double jump with an elytra in creative mode

line 20 of LivingEntityMixin
    @Redirect(method = "travel", at = @At(value = "INVOKE", target = "Lnet/minecraft/world/entity/LivingEntity;onGround()Z", ordinal = -2))
	
line 83 of LocalPlayerMixin found somewhere in common
setDeltaMovement(getDeltaMovement().add(0, -Math.sin(Math.toRadians(getXRot())) * input.forwardImpulse * getFlyingSpeed() * 2, 0));