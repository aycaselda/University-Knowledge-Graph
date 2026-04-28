# Knowledge-Engineering-Ontology-Project

This project was developed as part of the Knowledge Engineering and Ontologies course to model the semantic relationships within a university ecosystem.

## Project-Team

Ayça Selda Keskin / 220316054  
Efe Şamil Sarıgül / 220316050

## Purpose-and-Scope

The purpose of this ontology is to formalize semantic relationships such as student enrollments, faculty teaching assignments, and course prerequisite structures to enable automated academic reasoning and querying. The scope is limited to core academic entities:

* **Persons:** Students and Teachers.
* **Courses:** Academic subjects and their prerequisite hierarchies.
* **Departments:** Academic affiliations.
* **Academic Terms:** Semesters or terms.

## Technical-Specifications

* **Ontology Language:** OWL 2 (Web Ontology Language) / RDF.
* **Development Tool:** Protégé.
* **Reasoning Support:** Designed for reasoners like HermiT or Pellet.

## Ontology-Structure

**Core Classes**
* **person:** The base class for individuals.
* **student:** Individuals enrolled in courses.
* **professors:** Individuals responsible for teaching.
* **course:** Academic subjects.
* **department:** University departments.
* **academicTerm:** Specific periods of study.

**Object-Properties**
* **belongsTo:** Connects a person to a department.
* **hasPrerequisite:** Defines prerequisite relationships between courses (Transitive property).
* **isEnrolledIn:** Connects a student to a course.
* **teaches:** Connects a professor to a course.

## Competency-Questions (CQs)

The system is designed to answer the following questions: 
1. What are the prerequisite courses for a specific Course?
2. Which Department does a specific Student belong to?
3. Is a specific Student enrolled in a specific Course? 
4. Which Courses are taught by a specific Teacher?

## Example-Instances (Individuals)

The ontology includes several initial instances for testing: 
* **Students:** Ayca Keskin, Efe Sarıgül, Sinem, and Özgür. 
* **Professors:** Can, Gamze, and Nihat.
* **Courses:** Automata Theory, Physics, Knowledge Engineering and Ontologies, Operating Systems, and Mathematics.

## Usage

You can open the `university-knowledge-graph.rdf` file using Protégé to explore the classes, properties, and individuals, or to run SPARQL queries for data analysis.
