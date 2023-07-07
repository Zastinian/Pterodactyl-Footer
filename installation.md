Upload the one in the pterodactyl folder in the /var/www/pterodactyl folder of your vps

Open /var/www/pterodactyl/resources/scripts/components/auth/LoginFormContainer.tsx

Put under import tw from 'twin.macro';

import {login_footer} from "../../../../public/hedystia/footer";

Search

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

Replace it with

<p css={tw`text-center text-neutral-500 text-xs mt-4`}>
      <a rel={"noopener nofollow noreferrer"} target={"_blank"} css={tw`no-underline text-neutral-500 hover:text-neutral-300`}>
        {login_footer}
      </a>
    </p>

Open /var/www/pterodactyl/resources/scripts/components/elements/PageContentBlock.tsx

Put under import tw from 'twin.macro';

import {dash_footer} from "../../../../public/hedystia/footer";

Search

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

Replace it with

        <ContentContainer css={tw`mb-4`}>
          <p css={tw`text-center text-neutral-500 text-xs`}>
            <a rel={"noopener nofollow noreferrer"} target={"_blank"} css={tw`no-underline text-neutral-500 hover:text-neutral-300`}>
              {dash_footer}
            </a>
          </p>
        </ContentContainer>

How to put the custom footer

Use

nano /var/www/pterodactyl/public/hedystia/footer.tsx

Search
export const dash_footer = "Pterodactyl | Power by Hedystia Addons";
export const login_footer = "Pterodactyl | Power by Hedystia Addons";

Replace the text "Pterodactyl | Power by Hedystia Addons" with what you want to display as "My Panel" example

Save and close the file

Final commands (ONLY TESTED ON UBUNTU, MAY NOT WORK ON OTHER OPERATING SYSTEMS):

cd /var/www/pterodactyl
php artisan down
php artisan migrate --seed --force
yarn install
yarn build:production
php artisan config:cache
php artisan view:cache
php artisan queue:restart
php artisan up

Once set, if it does not load, use control + f5 3 or 4 times to reload the page cache and load correctly.

If you have any questions, you can contact me at the following discord server:

https://discord.gg/aXvuUpvRQs
