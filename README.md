# @alibee/react-modal

Un composant de fenêtre modale simple, léger et personnalisable pour React.

[![npm version](https://img.shields.io/npm/v/@alibee/react-modal.svg)](https://www.npmjs.com/package/@alibee/react-modal)
[![license](https://img.shields.io/npm/l/@alibee/react-modal.svg)](https://github.com/Babali61/react-modal/blob/main/LICENSE)

## 📦 Installation

```bash
npm install @alibee/react-modal
# ou
yarn add @alibee/react-modal
```

## 🔧 Utilisation basique

```jsx
import { Modal } from '@alibee/react-modal';
import '@alibee/react-modal/dist/style.css';

function App() {
  const [isOpen, setIsOpen] = useState(false);

  return (
    <div>
      <button onClick={() => setIsOpen(true)}>
        Ouvrir la modale
      </button>

      <Modal
        isOpen={isOpen}
        onClose={() => setIsOpen(false)}
        title="Titre de la modale"
        size="md"
      >
        <p>Contenu de votre modale ici</p>
      </Modal>
    </div>
  );
}
```

## 🎯 Exemple d'utilisation réel

Voici un exemple d'utilisation dans une application de gestion des ressources humaines :

```jsx
import { useState } from 'react';
import { Modal } from '@alibee/react-modal';
import '@alibee/react-modal/dist/style.css';

function CreateEmployee() {
  const [isModalOpen, setIsModalOpen] = useState(false);
  
  // Boutons personnalisés pour le pied de page
  const modalFooter = (
    <>
      <button 
        onClick={() => navigate('/employee-list')}
        className="button button-primary"
      >
        Voir la liste des employés
      </button>
      <button 
        onClick={() => setIsModalOpen(false)}
        className="button button-danger"
      >
        Fermer
      </button>
    </>
  );

  return (
    <div>
      {/* Votre formulaire ici */}
      
      <Modal 
        isOpen={isModalOpen} 
        onClose={() => setIsModalOpen(false)}
        title="Employé créé"
        size="md"
        footer={modalFooter}
        closeOnEscape={true}
        closeOnClickOutside={true}
      >
        <div className="message message-success">
          L'employé a été créé avec succès et ajouté à la liste des employés.
        </div>
        <p>
          Vous pouvez maintenant créer un autre employé ou consulter la liste des employés existants à l'aide des boutons ci-dessous.
        </p>
      </Modal>
    </div>
  );
}
```

## 🎨 Props

| Prop | Type | Par défaut | Description |
|------|------|------------|-------------|
| `isOpen` | `boolean` | Requis | Contrôle l'état d'ouverture de la modale |
| `onClose` | `() => void` | Requis | Fonction appelée lors de la fermeture |
| `children` | `ReactNode` | Requis | Contenu à afficher dans le modal |
| `className` | `string` | `''` | Classes CSS additionnelles |
| `closeOnEscape` | `boolean` | `true` | Si true, le modal se ferme avec la touche Escape |
| `closeOnClickOutside` | `boolean` | `true` | Si true, le modal se ferme en cliquant à l'extérieur |
| `size` | `'sm' \| 'md' \| 'lg'` | `'md'` | Taille du modal |
| `footer` | `ReactNode` | - | Contenu du pied de modal (optionnel) |
| `title` | `string` | - | Titre du modal (optionnel) |

## 🎨 Personnalisation

Le composant Modal utilise des classes CSS que vous pouvez surcharger :

```css
.modal-overlay {
  /* Styles de l'overlay */
}

.modal {
  /* Styles du conteneur principal */
}

.modal-sm {
  /* Styles pour la taille small */
  max-width: 400px;
}

.modal-md {
  /* Styles pour la taille medium
  max-width: 550px;
}

.modal-lg {
  /* Styles pour la taille large */
  max-width: 700px;
}

.modal-title {
  /* Styles du titre */
}

.modal-content {
  /* Styles du contenu */
}

.modal-footer {
  /* Styles du pied de page */
}

.modal-close {
  /* Styles du bouton de fermeture */
}
```

## 📦 Versions

- React 16.8.0 ou supérieur
- React DOM 16.8.0 ou supérieur

## 🔒 Licence

MIT © [Babali61](https://github.com/Babali61) 