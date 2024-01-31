document.addEventListener('DOMContentLoaded', function () {
    // Premier formulaire
    function afficherPopup() {
        var prenom = document.monForm1.prenom.value;
        var nom = document.monForm1.nom.value;
        var sexe = document.monForm1.sexe.value;
        var livraison = document.monForm1.livraison.value;
        var papier = document.monForm1.papier.value;
        var naissanceJour = document.monForm1.naissanceJour.value;
        var naissanceMois = document.monForm1.naissanceMois.value;
        var naissanceAnne = document.monForm1.naissanceAnne.value;
        var adresse = document.monForm1.adresse.value;
        var postale = document.monForm1.postale.value;
        var ville = document.monForm1.ville.value;
        var pays = document.monForm1.pays.value;

        var message = "Prénom: " + prenom + "\nNom: " + nom + "\nSexe: " + sexe +
            "\nDate de livraison: " + livraison + "\nCouleur de papier: " + papier +
            "\nDate de naissance: " + naissanceJour + "/" + naissanceMois + "/" + naissanceAnne +
            "\nAdresse: " + adresse + "\nCode postal: " + postale + "\nVille: " + ville +
            "\nPays: " + pays;

        var popup = window.open('', 'popup', 'width=500,height=700');
        popup.document.write('<style>body { background-color: yellow; color: black; }</style>');
        popup.document.write('<pre>' + message + '</pre>');
        popup.document.write('<button onclick="window.close()">Fermer</button>');
    }

    var boutonEnvoyer = document.monForm1.querySelector('input[type="submit"]');
    boutonEnvoyer.addEventListener('click', afficherPopup);

    // Deuxième formulaire
    function afficherPopupForm2() {
        var identifiant = document.monForm2.identifiant.value;
        var password = document.monForm2.password.value;
        var site = document.monForm2.site.value;
        var email = document.monForm2.email.value;
        var questionSecrete = document.monForm2.secret.value;
        var reponse = document.monForm2.reponse.value;
        var vacances = document.monForm2.vacances.value;

        var message = "Identifiant: " + identifiant + "\nMot de passe: " + password +
            "\nAdresse du site: " + '<a href="' + site + '" target="_blank">' + site + '</a>' + '<span><a href="mailto:' + email + '">' + email + '</a></span>' +
            "\nQuestion secrète: " + questionSecrete + "\nRéponse: " + reponse +
            "\nVacances: " + vacances;

        var popup = window.open('', 'popup', 'width=500,height=700');
        popup.document.write('<pre>' + message + '</pre>');
        popup.document.write('<button onclick="window.close()">Fermer</button>');
    }

    var boutonEnvoyerForm2 = document.monForm2.querySelector('input[type="submit"]');
    boutonEnvoyerForm2.addEventListener('click', afficherPopupForm2);
});

document.addEventListener('DOMContentLoaded', function () {
    // Vérification du champ de recherche
    function verifierChampRecherche() {
        var champRecherche = document.querySelector('input[type="search"]');
        var valeurChampRecherche = champRecherche.value;

        if (valeurChampRecherche.search(/^[A-Za-z-]+$/) === -1) {
            alert("Le champ de recherche doit contenir uniquement des lettres majuscules, minuscules ou des traits d'union.");
            return;
        }

        console.log("Valeur du champ de recherche:", valeurChampRecherche);
    }

    var boutonRecherche = document.querySelector('button[type="button"]');
    boutonRecherche.addEventListener('click', verifierChampRecherche);
});