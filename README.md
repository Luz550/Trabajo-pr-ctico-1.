using System;

public abstract class Operator
public abstract class Operator

{

	protected int id; protected int battery; protected int state; protected int maxLoad;

	protected int speed;

	public Operator(int id, int battery, int state, int maxLoad, int speed, string location)

	{

		this.id = id;

		this.battery = battery;

		this.state = state;

		this.maxLoad = maxLoad;

		this.speed = speed;

	}

	public virtual void Move(int kilometers)

	{

		// Lógica común para moverse

	}

}
public class UAV : Operator

{

	public UAV(int id, int battery, int state, int maxLoad, int speed, string location)

	: base(id, battery, state, maxload, speed, location)

	{

	}

	public override void Move(int kilometers)

	{

		double batteryConsumption = kilometers * 0.025;

		double speedReduction = Math.Pow(1 - (battery / 100.0), 0.2);

		double stateReduction = Math.Pow(1 - (battery / 100.0), 0.04);

		battery = (int)batteryConsumption;

		speed = (int)Math.Min(speed speedReduction, speed);

		state -= (int)stateReduction;

		base.Move(kilometers);

	}

	public static void Main()

	{

		// Punto de entrada para la aplicación

	}

}

//Matilda Sosa.