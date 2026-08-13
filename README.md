# Portfolio Académique — Aissatou Kébé

Portfolio personnel réalisé en HTML, CSS, JavaScript et PHP, avec une base
de données MySQL pour l'affichage dynamique des projets (avec galerie
d'images) et l'enregistrement des messages de contact.

Site en ligne : https://aissatouportfolio.lovestoblog.com

## Structure

```
portfolio/
├── index.php              Page d'accueil (profil + photo, style deux-moitiés)
├── apropos.php             Page À propos (résumé + CV en PDF téléchargeable)
├── projets.php             Liste des projets (récupérés depuis MySQL, galerie au clic)
├── contact.php             Formulaire de contact (enregistre en base)
├── config/
│   └── db.php                Connexion PDO à la base de données MySQL
├── includes/
│   ├── header.php             En-tête + navigation (inclus sur chaque page publique)
│   └── footer.php             Pied de page (coordonnées, réseaux)
├── css/
│   └── style.css              Styles (thème rose, Space Grotesk, responsive mobile)
├── js/
│   └── script.js              Menu mobile, galerie interactive, validation du formulaire
├── assets/
│   ├── img/                    Photos et images des projets
│   └── cv/                     CV en PDF
├── sql/
│   └── portfolio-mysql.sql     Script de création des tables (MySQL)
└── admin/                    Espace d'administration (géré en local uniquement,
                                non déployé sur l'hébergement public)
```

## Espace admin

L'espace `admin/` (ajout de projets, consultation des messages) est utilisé
en local uniquement, connecté à une base MySQL locale (XAMPP). Les nouveaux
projets ajoutés localement doivent être synchronisés manuellement vers la
base de production (export/import via phpMyAdmin) pour apparaître sur le
site en ligne.

## Installation locale

1. Installer XAMPP (Apache + PHP + MySQL).
2. Créer la base de données via phpMyAdmin (`http://localhost/phpmyadmin`)
   et importer `sql/portfolio-mysql.sql`.
3. Adapter les identifiants dans `config/db.php` si besoin.
4. Placer le dossier du projet dans `htdocs`, puis ouvrir `index.php` dans
   le navigateur.
5. Pour créer le compte admin, utiliser temporairement un script
   `creer-compte.php` (à générer, mot de passe haché avec `password_hash()`),
   puis le supprimer après usage.

## Déploiement

Seules les pages publiques (hors `admin/`) sont envoyées sur l'hébergement
(InfinityFree). La base de données de production est une base MySQL
fournie par l'hébergeur, distincte de la base locale.
