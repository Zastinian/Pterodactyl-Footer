Sube la que esta en la carpeta pterodactyl en la carpeta /var/www/pterodactyl de su vps

Abre /var/www/pterodactyl/resources/scripts/components/auth/LoginFormContainer.tsx

Pon debajo de import tw from 'twin.macro';

import {login_footer} from "../../../../public/hedystia/footer";

Busca

<p css={tw`text-center text-neutral-500 text-xs mt-4`}>
            &copy; 2015 - {new Date().getFullYear()}&nbsp;
            <a
                rel={'noopener nofollow noreferrer'}
                href={'https://pterodactyl.io'}
                target={'_blank'}
                css={tw`no-underline text-neutral-500 hover:text-neutral-300`}
            >
                Pterodactyl Software
            </a>
        </p>

Remplazalo por

<p css={tw`text-center text-neutral-500 text-xs mt-4`}>
      <a rel={"noopener nofollow noreferrer"} target={"_blank"} css={tw`no-underline text-neutral-500 hover:text-neutral-300`}>
        {login_footer}
      </a>
    </p>

Abre /var/www/pterodactyl/resources/scripts/components/elements/PageContentBlock.tsx

Pon debajo de import tw from 'twin.macro';

import {dash_footer} from "../../../../public/hedystia/footer";

Busca

            <ContentContainer css={tw`mb-4`}>
                <p css={tw`text-center text-neutral-500 text-xs`}>
                    <a
                        rel={'noopener nofollow noreferrer'}
                        href={'https://pterodactyl.io'}
                        target={'_blank'}
                        css={tw`no-underline text-neutral-500 hover:text-neutral-300`}
                    >
                        Pterodactyl&reg;
                    </a>
                    &nbsp;&copy; 2015 - {new Date().getFullYear()}
                </p>
            </ContentContainer>

Remplazalo por

        <ContentContainer css={tw`mb-4`}>
          <p css={tw`text-center text-neutral-500 text-xs`}>
            <a rel={"noopener nofollow noreferrer"} target={"_blank"} css={tw`no-underline text-neutral-500 hover:text-neutral-300`}>
              {dash_footer}
            </a>
          </p>
        </ContentContainer>

Como poner el footer personalizado

Usa

nano /var/www/pterodactyl/public/hedystia/footer.tsx

Busca
export const dash_footer = "Pterodactyl | Power by Hedystia Addons";
export const login_footer = "Pterodactyl | Power by Hedystia Addons";

Reemplaza el texto "Pterodactyl | Power by Hedystia Addons" por lo que quieres que salga ejemplo "My Panel"

Guarda y cierra el archivo

Comandos finales (SÓLO PROBADOS EN UBUNTU, PUEDE QUE NO FUNCIONEN EN OTRO SISTEMA OPERATIVO):

cd /var/www/pterodactyl
php artisan down
php artisan migrate --seed --force
yarn install
yarn build:production
php artisan config:cache
php artisan view:cache
php artisan queue:restart
php artisan up

Una vez puesto si no te carga debes usar control + f5 de 3 a 4 veces para recargar el cache de la pagina y ya te cargue correctamente.

Si tienes alguna duda, puedes contactar conmigo en el siguiente servidor de discord:

https://discord.gg/aXvuUpvRQs
