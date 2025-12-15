# Configuration EmailJS pour le Formulaire de Contact

## 📧 EmailJS - Service d'envoi d'emails gratuit et sécurisé

EmailJS permet d'envoyer des emails directement depuis le navigateur sans backend. C'est gratuit jusqu'à 200 emails/mois.

## 🚀 Étapes de Configuration

### 1. Créer un compte EmailJS

1. Va sur [EmailJS](https://www.emailjs.com/)
2. Clique sur **"Sign Up"** pour créer un compte gratuit
3. Confirme ton email

### 2. Créer un Service Email

1. Dans le dashboard, clique sur **"Email Services"**
2. Clique sur **"Add New Service"**
3. Choisis ton fournisseur d'email (Gmail recommandé):
   - **Gmail**: Connecte ton compte Gmail (marwan.seghiri.77@gmail.com)
   - Ou utilise un autre service (Outlook, Yahoo, etc.)
4. Note le **Service ID** (ex: `service_abc123`)

### 3. Créer un Template d'Email

1. Va dans **"Email Templates"**
2. Clique sur **"Create New Template"**
3. Configure le template avec ces variables:

**Sujet de l'email:**
```
Nouveau message de {{user_name}} - {{subject}}
```

**Contenu de l'email:**
```
Vous avez reçu un nouveau message depuis votre portfolio:

Nom: {{user_name}}
Email: {{user_email}}
Téléphone: {{user_phone}}
Sujet: {{subject}}

Message:
{{message}}

---
Ce message a été envoyé depuis votre formulaire de contact.
```

4. Dans les paramètres:
   - **To Email**: marwan.seghiri.77@gmail.com
   - **From Name**: Portfolio Contact Form
   - **Reply To**: {{user_email}}

5. Sauvegarde et note le **Template ID** (ex: `template_xyz789`)

### 4. Obtenir la Clé Publique

1. Va dans **"Account"** → **"General"**
2. Copie ta **Public Key** (ex: `aBcDeFgHiJkLmNoPqR`)

### 5. Configurer le Code

Dans le fichier `app.js`, remplace les 3 valeurs suivantes:

```javascript
// Ligne 8: Remplace YOUR_PUBLIC_KEY
emailjs.init("aBcDeFgHiJkLmNoPqR"); // Ta clé publique

// Ligne 33: Remplace YOUR_SERVICE_ID et YOUR_TEMPLATE_ID
emailjs.send('service_abc123', 'template_xyz789', templateParams)
```

**Exemple complet:**
```javascript
emailjs.init("aBcDeFgHiJkLmNoPqR");
emailjs.send('service_abc123', 'template_xyz789', templateParams)
```

## ✅ Tester le Formulaire

1. Ouvre `index.html` dans ton navigateur
2. Va à la section "Contact"
3. Remplis le formulaire et envoie
4. Tu devrais recevoir un email à: marwan.seghiri.77@gmail.com
5. Un message de succès vert s'affiche

## 🔒 Sécurité

✅ **EmailJS est sécurisé:**
- La clé publique peut être exposée (c'est normal)
- Protection anti-spam intégrée
- Limite de 200 emails/mois (gratuit)
- reCAPTCHA optionnel disponible

✅ **Validation du formulaire:**
- Champs obligatoires (nom, email, sujet, message)
- Validation HTML5 native
- Prévention de spam avec limite de taux

## 🎨 Fonctionnalités

✅ Envoi d'email vers: marwan.seghiri.77@gmail.com
✅ Message de succès/erreur
✅ Bouton désactivé pendant l'envoi
✅ Reset automatique du formulaire
✅ Design cohérent avec le portfolio
✅ Responsive mobile/tablette/desktop

## 🆓 Alternatives Gratuites

Si tu veux d'autres options:

1. **Formspree** - 50 emails/mois gratuit
2. **Getform** - 100 emails/mois gratuit
3. **FormSubmit** - Illimité mais moins de fonctionnalités

## 📞 Support

Si tu as des problèmes:
- Vérifie la console du navigateur (F12)
- Vérifie que les 3 IDs sont corrects
- Vérifie que le service Gmail est bien connecté
- Teste avec un autre email pour vérifier

---

**Note:** N'oublie pas de remplacer les valeurs dans `app.js` avant de déployer! 🚀
