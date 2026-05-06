
        {!profil && (
          <>
            {step === 1 && (
              <div>
                <p>As-tu un logement stable ?</p>
                <select name="logement" onChange={handleChange} className="w-full p-2 border rounded">
                  <option value="">Choisir</option>
                  <option value="stable">Oui</option>
                  <option value="instable">Non</option>
                </select>
              </div>
            )}

            {step === 2 && (
              <div>
                <p>Ta santé est-elle suivie ?</p>
                <select name="sante" onChange={handleChange} className="w-full p-2 border rounded">
                  <option value="">Choisir</option>
                  <option value="ok">Oui</option>
                  <option value="non">Non</option>
                </select>
              </div>
            )}

            {step === 3 && (
              <div>
                <p>Peux-tu te déplacer facilement ?</p>
                <select name="mobilite" onChange={handleChange} className="w-full p-2 border rounded">
                  <option value="">Choisir</option>
                  <option value="ok">Oui</option>
                  <option value="non">Non</option>
                </select>
              </div>
            )}

            {step === 4 && (
              <div>
                <p>As-tu un projet professionnel ?</p>
                <select name="projet" onChange={handleChange} className="w-full p-2 border rounded">
                  <option value="">Choisir</option>
                  <option value="clair">Oui</option>
                  <option value="flou">Non</option>
                </select>
              </div>
            )}

            {step === 5 && (
              <div>
                <p>Note tes compétences (0-10)</p>
                <input type="number" name="competences" min="0" max="10" onChange={handleChange} className="w-full p-2 border rounded" />
              </div>
            )}

            {step === 6 && (
              <div>
                <p>Situation financière stable ?</p>
                <select name="finance" onChange={handleChange} className="w-full p-2 border rounded">
                  <option value="">Choisir</option>
                  <option value="ok">Oui</option>
                  <option value="non">Non</option>
                </select>
              </div>
            )}

            <div className="flex justify-between mt-6">
              {step > 1 && (
                <button onClick={prev} className="px-4 py-2 bg-gray-300 rounded">Retour</button>
              )}

              {step < 6 ? (
                <button onClick={next} className="px-4 py-2 bg-blue-500 text-white rounded ml-auto">Suivant</button>
              ) : (
                <button onClick={submit} className="px-4 py-2 bg-green-500 text-white rounded ml-auto">Résultat</button>
              )}
            </div>
          </>
        )}

        {profil && (
          <div>
            <h2 className="text-lg font-bold mb-2">
              Profil : {profil.toUpperCase()}
            </h2>

            <p className="mb-2">Dispositifs recommandés :</p>
            <ul className="list-disc pl-5">
              {recommandations(profil).map((item, i) => (
                <li key={i}>{item}</li>
              ))}
            </ul>
          </div>
        )}
      </div>
    </div>
  );
}

     
