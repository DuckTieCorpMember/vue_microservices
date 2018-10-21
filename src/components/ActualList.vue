<template>
    <div class="layout">
        <div class="layout__block shrink">
            <div class="control-bar control-bar--sub">
                <div class="control-bar__layout shrink">
                    <div class="search">
                        <button type="button" class="search__button button">
                            <span class="button__icon icon icon--baseline">
                                <svg class="icon__svg" viewBox="0 0 31 31" version="1.1">
                                    <path d="M20.797,13.185c0,-2.095 -0.745,-3.888 -2.234,-5.377c-1.49,-1.49 -3.282,-2.235 -5.378,-2.235c-2.095,0 -3.888,0.745 -5.377,2.235c-1.49,1.489 -2.235,3.282 -2.235,5.377c0,2.096 0.745,3.888 2.235,5.378c1.489,1.489 3.282,2.234 5.377,2.234c2.096,0 3.888,-0.745 5.378,-2.234c1.489,-1.49 2.234,-3.282 2.234,-5.378Zm8.699,14.136c0,0.589 -0.215,1.099 -0.645,1.53c-0.431,0.43 -0.941,0.645 -1.53,0.645c-0.611,0 -1.121,-0.215 -1.529,-0.645l-5.828,-5.811c-2.027,1.404 -4.287,2.107 -6.779,2.107c-1.62,0 -3.169,-0.315 -4.647,-0.943c-1.478,-0.629 -2.752,-1.479 -3.823,-2.549c-1.07,-1.07 -1.92,-2.345 -2.548,-3.823c-0.629,-1.478 -0.943,-3.027 -0.943,-4.647c0,-1.62 0.314,-3.169 0.943,-4.647c0.628,-1.478 1.478,-2.752 2.548,-3.823c1.071,-1.07 2.345,-1.92 3.823,-2.548c1.478,-0.629 3.027,-0.943 4.647,-0.943c1.62,0 3.169,0.314 4.647,0.943c1.478,0.628 2.753,1.478 3.823,2.548c1.07,1.071 1.92,2.345 2.549,3.823c0.628,1.478 0.943,3.027 0.943,4.647c0,2.492 -0.703,4.752 -2.107,6.779l5.828,5.828c0.419,0.419 0.628,0.929 0.628,1.529Z"></path>
                                </svg>
                            </span>
                        </button>
                        <input class="search__input" placeholder="Enter service ..."/>
                        <button type="button" class="search__clear-button button">
                            <span class="button__icon icon icon--baseline">
                                <svg class="icon__svg" viewBox="0 0 31 31" version="1.1">
                                    <path d="m 22.47134,19.635231 q 0,-0.475735 -0.347652,-0.823387 L 18.811844,15.5 22.123688,12.188156 q 0.347652,-0.347652 0.347652,-0.823387 0,-0.494032 -0.347652,-0.841684 L 20.476915,8.8763118 q -0.347652,-0.3476521 -0.841684,-0.3476521 -0.475735,0 -0.823387,0.3476521 L 15.5,12.188156 12.188156,8.8763118 q -0.347652,-0.3476521 -0.823387,-0.3476521 -0.494032,0 -0.841684,0.3476521 L 8.8763117,10.523085 q -0.3476519,0.347652 -0.3476519,0.841684 0,0.475735 0.3476519,0.823387 L 12.188156,15.5 8.8763117,18.811844 q -0.3476519,0.347652 -0.3476519,0.823387 0,0.494032 0.3476519,0.841684 l 1.6467733,1.646773 q 0.347652,0.347652 0.841684,0.347652 0.475735,0 0.823387,-0.347652 L 15.5,18.811844 l 3.311844,3.311844 q 0.347652,0.347652 0.823387,0.347652 0.494032,0 0.841684,-0.347652 l 1.646773,-1.646773 Q 22.47134,20.129263 22.47134,19.635231 Z M 29.552465,15.5 q 0,3.824174 -1.88464,7.053679 -1.88464,3.229506 -5.114146,5.114146 -3.229505,1.88464 -7.053679,1.88464 -3.824174,0 -7.0536791,-1.88464 Q 5.2168155,25.783185 3.332175,22.553679 1.4475342,19.324174 1.4475342,15.5 q 0,-3.824174 1.8846408,-7.053679 Q 5.2168155,5.2168155 8.4463209,3.332175 11.675826,1.4475342 15.5,1.4475342 q 3.824174,0 7.053679,1.8846408 3.229506,1.8846405 5.114146,5.114146 1.88464,3.229505 1.88464,7.053679 z">
                                    </path>
                                </svg>
                            </span>
                        </button>
                    </div>
                </div>
                <div class="control-bar__layout">
                    <button class="button">Add service</button>
                </div>
            </div>
        </div>
        <div class="layout__block">
            <div class="layout__row">
                <div class="layout__block shrink">
                    <div class="service-list">
                        <div class="service-list__header">
                            <span class="text-large bold">Service List</span>
                        </div>
                        <div class="service-list__body">
                            <ul class="list">
                                <li class="list__layout">AAAAAAAAAAAA</li>
                            </ul>
                        </div>
                    </div>
                </div>
                <div class="layout__block">
                    <div class="layout__table">
                        <table class="table table--details">
                            <thead class="table__thead">
                                <tr class="table__row">
                                    <th class="table__th table__th--nowrap">
                                        <span class="text-large bold">Details</span>
                                    </th>
                                    <th class="table__th">
                                        <div class="panel">
                                            <div class="panel__layout shrink">
                                                <button class="button">Edit</button>
                                            </div>
                                            <div class="panel_layout">
                                                <button class="button">Delete</button>
                                            </div>
                                        </div>
                                    </th>
                                </tr>
                            </thead>
                            <tbody class="table__tbody">
                                <tr class="table__row">
                                    <td class="table__td table__td--txt-right table__td--nowrap">Name</td>
                                    <td class="table__td">AAAAAAAAAA</td>
                                </tr>
                                <tr class="table__row">
                                    <td class="table__td table__td--txt-right">Description</td>
                                    <td class="table__td">nooooooooooooooooooo ononon ni ni ni noi gno nio fdoign dfng ifdnio gndfin giofdng iofdniog ndfion</td>
                                </tr>
                                <tr class="table__row">
                                    <td class="table__td table__td--txt-right">Projects</td>
                                    <td class="table__td">
                                        <div class="panel">
                                            <ul>
                                                <li style="float: left;" class="panel__layout shrink"><a class="link">Asd</a></li>
                                                <li style="float: left;" class="panel__layout shrink"><a class="link">Asd</a></li>
                                                <li style="float: left;" class="panel__layout shrink"><a class="link">Asd</a></li>
                                            </ul>
                                        </div>
                                    </td>
                                </tr>
                                <tr class="table__row">
                                    <td class="table__td table__td--txt-right">End Points</td>
                                    <td class="table__td">AAAAAAAAAA</td>
                                </tr>
                                <tr class="table__row">
                                    <td class="table__td table__td--txt-right">Git</td>
                                    <td class="table__td"><a class="link">GIT</a></td>
                                </tr>
                                <tr class="table__row">
                                    <td class="table__td table__td--txt-right">.JARs</td>
                                    <td class="table__td">
                                        <div class="panel">
                                            <ul>
                                                <li style="float: left;" class="panel__layout shrink"><a class="link">Asd.jar</a></li>
                                                <li style="float: left;" class="panel__layout shrink"><a class="link">Asd.jar</a></li>
                                                <li style="float: left;" class="panel__layout shrink"><a class="link">Asd.jar</a></li>
                                            </ul>
                                        </div>
                                    </td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
    @import './css/service_list.css';
</style>