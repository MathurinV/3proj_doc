# cache

The cache service uses a redis image to store data in ram. This service allows the back to generate secured tokens to be consumed by the client.
At the start of the project, this service was not intended to be used, but since the api uses a graphql engine, we found it more practical to serve files statically, using more traditional ways.
Therefore, the cache stores:
<tabs>
    <tab title="Sensible data tokens">
        When accessing and uploading sensible data, the api first gives the user access to a mutation that handles the authentication. If authentication is valid, it returns an url composed of the controller name and a unique token stored inside redis.
        <tabs>
            <tab title="Justifications">
                A new token is generated when an authorized user wants to upload or download a justification.
                We want the justifications to be secured, since personal data can be included in it.
                Therefore, the following token is generated:
            <table>
                <tr>
                    <th>Key</th>
                    <th>Value</th>
                </tr>
                <tr>
                    <th>Guid token</th>
                    <th>Guid expenseId</th>
                </tr>
            </table>
            </tab>
            <tab title="Group Sum-up">
                A new token is generated when an authorized user (user member of the queried group) wants to access a sum-up of a group.
                We want the sum-up to be secured, since personal data can be included in it.
                Therefore, the following token is generated:
                <table>
                    <tr>
                        <th>Key</th>
                        <th>Value</th>
                    </tr>
                    <tr>
                        <th>Guid token</th>
                        <th>Guid groupId</th>
                    </tr>
                </table>
            </tab>
            <tab title="Group Sum-up">
                A new token is generated when an authorized user (user logged in) wants to access his sum-up.
                We want the sum-up to be secured, since personal data is included in it.
                Therefore, the following token is generated:
                <table>
                    <tr>
                        <th>Key</th>
                        <th>Value</th>
                    </tr>
                    <tr>
                        <th>Guid token</th>
                        <th>Guid userId</th>
                    </tr>
                </table>
            </tab>
            <tab title="Ribs">
                A new token is generated when an authorized user wants to upload or download a rib.
                We want the rib to be secured, since personal data is included in it.
                Therefore, the following token is generated:
                <table>
                    <tr>
                        <th>Key</th>
                        <th>Value</th>
                    </tr>
                    <tr>
                        <th>Guid token</th>
                        <th>Guid userId</th>
                    </tr>
                </table>            
            </tab>
        </tabs>
    </tab>
    <tab title="Not sensible data tokens">
        Not sensitive data upload is handled the same way, but accessing the resource is handled directly by graphQl Api, without the help of redis
        <tabs>
            <tab title="Avatars">
                <table>
                    <tr>
                    <th>Key</th>
                    <th>Value</th>
                    </tr>
                    <tr>
                    <th>Guid token</th>
                    <th>Guid userId</th>
                    </tr>
                </table>
            </tab>
            <tab title="Group Image">
                <table>
                    <tr>
                    <th>Key</th>
                    <th>Value</th>
                    </tr>
                    <tr>
                    <th>Guid token</th>
                    <th>Guid groupId</th>
                    </tr>
                </table>
            </tab>
            </tabs>
    </tab>
</tabs>