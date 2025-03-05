Liskov Substitution Principle (LSP) - Principio de Sustitución de Liskov
// Incorrecto: La clase derivada cambia el comportamiento esperado del método de la clase base.
public class Bird
{
    public virtual void Fly()
    {
        Console.WriteLine("El ave está volando.");
    }
}

public class Penguin : Bird
{
    public override void Fly()
    {
        throw new NotImplementedException("Los pingüinos no vuelan.");
    }
}

// Correcto: Separar aves que vuelan de las que no vuelan.
public abstract class Bird { }

public interface IFlyingBird
{
    void Fly();
}

public class Sparrow : Bird, IFlyingBird
{
    public void Fly() => Console.WriteLine("El gorrión vuela.");
}

public class Penguin : Bird
{
    public void Swim() => Console.WriteLine("El pingüino nada.");
}
