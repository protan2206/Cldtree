import React, { useState } from 'react';
import { ChevronDown, ChevronUp, Plus, Trash2, Edit2, X } from 'lucide-react';

export default function FamilyTree() {
  const [familyData, setFamilyData] = useState([
    {
      id: 1,
      name: 'John Smith',
      expanded: true,
      children: [
        {
          id: 2,
          name: 'Michael Smith',
          expanded: false,
          children: [
            { id: 5, name: 'David Smith', expanded: false, children: [] },
            { id: 6, name: 'Emma Smith', expanded: false, children: [] }
          ]
        },
        {
          id: 3,
          name: 'Sarah Smith',
          expanded: false,
          children: [
            { id: 7, name: 'Oliver Johnson', expanded: false, children: [] }
          ]
        }
      ]
    },
    {
      id: 4,
      name: 'Mary Williams',
      expanded: false,
      children: []
    }
  ]);

  const [editingId, setEditingId] = useState(null);
  const [editingName, setEditingName] = useState('');
  const [addingChildTo, setAddingChildTo] = useState(null);
  const [newChildName, setNewChildName] = useState('');

  const toggleExpand = (id, data) => {
    return data.map(person => {
      if (person.id === id) {
        return { ...person, expanded: !person.expanded };
      }
      if (person.children.length > 0) {
        return { ...person, children: toggleExpand(id, person.children) };
      }
      return person;
    });
  };

  const handleToggle = (id) => {
    setFamilyData(toggleExpand(id, familyData));
  };

  const updateName = (id, data, newName) => {
    return data.map(person => {
      if (person.id === id) {
        return { ...person, name: newName };
      }
      if (person.children.length > 0) {
        return { ...person, children: updateName(id, person.children, newName) };
      }
      return person;
    });
  };

  const handleEdit = (id) => {
    setEditingId(id);
    const person = findPerson(id, familyData);
    setEditingName(person?.name || '');
  };

  const handleSaveEdit = (id) => {
    if (editingName.trim()) {
      setFamilyData(updateName(id, familyData, editingName.trim()));
    }
    setEditingId(null);
    setEditingName('');
  };

  const deletePerson = (id, data) => {
    return data
      .filter(person => person.id !== id)
      .map(person => ({
        ...person,
        children: person.children.length > 0 ? deletePerson(id, person.children) : person.children
      }));
  };

  const handleDelete = (id) => {
    setFamilyData(deletePerson(id, familyData));
  };

  const addChild = (parentId, data) => {
    let nextId = Math.max(...getAllIds(data)) + 1;
    
    return data.map(person => {
      if (person.id === parentId) {
        return {
          ...person,
          expanded: true,
          children: [
            ...person.children,
            { id: nextId, name: newChildName.trim(), expanded: false, children: [] }
          ]
        };
      }
      if (person.children.length > 0) {
        return { ...person, children: addChild(parentId, person.children) };
      }
      return person;
    });
  };

  const getAllIds = (data) => {
    let ids = [];
    data.forEach(person => {
      ids.push(person.id);
      if (person.children.length > 0) {
        ids = [...ids, ...getAllIds(person.children)];
      }
    });
    return ids;
  };

  const handleAddChild = (parentId) => {
    if (newChildName.trim()) {
      setFamilyData(addChild(parentId, familyData));
      setNewChildName('');
      setAddingChildTo(null);
    }
  };

  const findPerson = (id, data) => {
    for (let person of data) {
      if (person.id === id) return person;
      if (person.children.length > 0) {
        const found = findPerson(id, person.children);
        if (found) return found;
      }
    }
    return null;
  };

  const renderPerson = (person, level = 0) => {
    const hasChildren = person.children.length > 0;

    return (
      <div key={person.id} className="mb-2">
        <div className={`flex items-center gap-2 p-2 rounded-lg ${level === 0 ? 'bg-blue-50' : 'bg-gray-50'} hover:bg-gray-100 transition`}>
          {hasChildren && (
            <button
              onClick={() => handleToggle(person.id)}
              className="flex-shrink-0 p-1 hover:bg-gray-200 rounded"
            >
              {person.expanded ? (
                <ChevronUp size={18} className="text-blue-600" />
              ) : (
                <ChevronDown size={18} className="text-gray-600" />
              )}
            </button>
          )}
          {!hasChildren && <div className="w-7"></div>}

          {editingId === person.id ? (
            <div className="flex-grow flex gap-1">
              <input
                type="text"
                value={editingName}
                onChange={(e) => setEditingName(e.target.value)}
                className="flex-grow px-2 py-1 border border-blue-400 rounded text-sm"
                autoFocus
              />
              <button
                onClick={() => handleSaveEdit(person.id)}
                className="px-2 py-1 bg-green-500 text-white rounded text-sm hover:bg-green-600"
              >
                Save
              </button>
              <button
                onClick={() => setEditingId(null)}
                className="px-2 py-1 bg-gray-400 text-white rounded text-sm hover:bg-gray-500"
              >
                Cancel
              </button>
            </div>
          ) : (
            <>
              <span className="flex-grow font-medium text-gray-800 text-sm md:text-base">
                {person.name}
              </span>
              <button
                onClick={() => handleEdit(person.id)}
                className="p-1 text-blue-600 hover:bg-blue-100 rounded"
                title="Edit"
              >
                <Edit2 size={16} />
              </button>
              <button
                onClick={() => setAddingChildTo(person.id)}
                className="p-1 text-green-600 hover:bg-green-100 rounded"
                title="Add child"
              >
                <Plus size={16} />
              </button>
              {familyData.length > 1 && level > 0 && (
                <button
                  onClick={() => handleDelete(person.id)}
                  className="p-1 text-red-600 hover:bg-red-100 rounded"
                  title="Delete"
                >
                  <Trash2 size={16} />
                </button>
              )}
            </>
          )}
        </div>

        {addingChildTo === person.id && (
          <div className="ml-6 mt-2 p-2 bg-green-50 rounded-lg mb-2">
            <div className="flex gap-1 flex-col md:flex-row">
              <input
                type="text"
                placeholder="Child's name"
                value={newChildName}
                onChange={(e) => setNewChildName(e.target.value)}
                className="flex-grow px-2 py-1 border border-green-400 rounded text-sm"
                onKeyPress={(e) => e.key === 'Enter' && handleAddChild(person.id)}
              />
              <button
                onClick={() => handleAddChild(person.id)}
                className="px-3 py-1 bg-green-500 text-white rounded text-sm hover:bg-green-600 whitespace-nowrap"
              >
                Add
              </button>
              <button
                onClick={() => setAddingChildTo(null)}
                className="px-2 py-1 bg-gray-400 text-white rounded text-sm hover:bg-gray-500"
              >
                <X size={16} />
              </button>
            </div>
          </div>
        )}

        {person.expanded && hasChildren && (
          <div className="ml-6 md:ml-8 border-l-2 border-gray-300 pl-2 mt-2">
            {person.children.map(child => renderPerson(child, level + 1))}
          </div>
        )}
      </div>
    );
  };

  return (
    <div className="min-h-screen bg-gradient-to-br from-blue-50 to-indigo-100 p-4 md:p-8">
      <div className="max-w-4xl mx-auto">
        <div className="bg-white rounded-lg shadow-lg p-4 md:p-6">
          <h1 className="text-2xl md:text-4xl font-bold text-gray-800 mb-2">
            Family Tree
          </h1>
          <p className="text-gray-600 mb-6 text-sm md:text-base">
            Click names to expand/collapse, edit, or add children. Click the trash icon to remove members.
          </p>

          <div className="space-y-2">
            {familyData.map(person => renderPerson(person))}
          </div>

          <button
            onClick={() => {
              const newId = Math.max(...getAllIds(familyData)) + 1;
              setFamilyData([
                ...familyData,
                { id: newId, name: 'New Person', expanded: false, children: [] }
              ]);
            }}
            className="mt-6 w-full px-4 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700 font-medium transition flex items-center justify-center gap-2"
          >
            <Plus size={20} />
            Add Root Person
          </button>
        </div>
      </div>
    </div>
  );
}
