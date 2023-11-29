# Using PMD

Pick a Java project from Github (see the [instructions](../sujet.md) for suggestions). Run PMD on its source code using any ruleset. Describe below an issue found by PMD that you think should be solved (true positive) and include below the changes you would add to the source code. Describe below an issue found by PMD that is not worth solving (false positive). Explain why you would not solve this issue.

You can use the default [rule base](https://github.com/pmd/pmd/blob/master/pmd-java/src/main/resources/rulesets/java/quickstart.xml) available on the source repository of PMD.

## Answer

Projet utilisé: https://gitlab.inria.fr/gazelle/applications/mixed/gazelle-tm

Vrai positif : gazelle-tm\gazelle-tm-ejb\src\main\java\net\ihe\gazelle\dao\GazelleDAO.java 	16 	Unused import 'net.ihe.gazelle.tm.systems.model.*'

L'erreur retournée nous signale qu'un import n'a pas été utilisé. Celui de vrait alors être supprimé.

Faux positif :
gazelle-tm\gazelle-tm-ejb\src\main\java\net\ihe\gazelle\documents\converter\DocumentToXmlConverter.java 	61 	Useless parentheses.

L'erreur nous signale qu'une parenthèse est manquante. Cependant, elle n'est pas présente à cause d'une préférence de style ce qui ne constitue pas uneréelle erreur.