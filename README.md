# Cr-a-Mode-Styliste-Virtuel-Aliment-par-l-IA
Créa-Mode utilise l'IA générative pour créer des tenues personnalisées en fonction de la morphologie, du style et des préférences des utilisateurs, offrant une expérience de conseil en image révolutionnaire.
import random

class CreModeStylisteVirtuel:
    def __init__(self):
        # Exemple de base de données de tenues
        self.tenues = {
            'casual': {
                'mince': ['jean slim, t-shirt blanc, baskets', 'robe légère, sandales'],
                'rond': ['pantalon droit, chemise en lin', 'jupe évasée, blouse fluide']
            },
            'professionnel': {
                'mince': ['costume ajusté, chemise blanche', 'robe crayon, talons'],
                'rond': ['blazer, pantalon droit, chemise', 'ensemble tailleur, chemisier soie']
            }
        }

    def recommander_tenue(self, morphologie, style, preferences):
        """
        Génère une recommandation de tenue basée sur la morphologie, le style et les préférences de l'utilisateur.
        """
        tenues_possibles = self.tenues.get(style, {}).get(morphologie, [])
        
        # Filtrer les tenues basées sur les préférences (ex: couleur, matière)
        tenues_filtrees = [tenue for tenue in tenues_possibles if all(pref in tenue for pref in preferences)]
        
        if tenues_filtrees:
            return random.choice(tenues_filtrees)
        else:
            return "Désolé, nous n'avons pas trouvé de tenue correspondant à vos critères."

# Exemple d'utilisation
styliste = CreModeStylisteVirtuel()
morphologie = 'mince'  # Exemple de morphologie
style = 'casual'  # Exemple de style
preferences = ['jean', 'blanc']  # Exemple de préférences

recommandation = styliste.recommander_tenue(morphologie, style, preferences)
print(f"Nous vous recommandons : {recommandation}")
