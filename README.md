# Schem

[![license](https://img.shields.io/github/license/Minestom/MinestomDataGenerator.svg)](LICENSE)

A schematic reader and writer library for Minestom. The library can read Sponge schematics versions 1-3, currently
it always writes as Sponge schematics version 1.

## Install

This fork of schem is not available on Maven Central. To use it in your project:

1. Clone the repository and build the JAR locally:
```bash
  git clone https://github.com/AdamBurdik/schem.git
  cd schem
  ./gradlew build
```
2. Locate the built jar file in the build/libs directory.
3. Add the jar to your project libs directory
4. Include the jar as a dependency:
```groovy
dependencies {
    implementation files("libs/schem-<version>.jar")
}
```

## Usage

Loading schematic from file
```java
SchematicReader reader = new SchematicReader();
Schematic = reader.read(Path.of("path/to/schematic.sponge3"));
```

Saving schematic to file
```java
SchematicWriter writer = new SchematicWriter();
writer.write(schematic, Path.of("path/to/save/schematic.sponge3");
```

Pasting schematic to instance
```java
RelativeBatch batch = schematic.build(Rotation.NONE, true);
batch.apply(instance, callback);
```

Creating schematic in instance
```java
SchematicBuilder builder = new SchematicBuilder();
builder.addBlock(0, 0, 0, block);
builder.setOffset(0, 5, 0);

Schematic schematic = builder.build();
```

## Credits
This is just fork of the original [schem library](https://github.com/hollow-cube/schem) to support minestom 1.21.2 and improve some stuff

## License

This project is licensed under the [MIT License](LICENSE).