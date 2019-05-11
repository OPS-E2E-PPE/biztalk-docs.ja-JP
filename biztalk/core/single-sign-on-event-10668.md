---
title: シングル サインオン:イベント 10668 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0eb3dd4d-04b5-4713-93c1-76af012d6920
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f9930c9c9f07c95ddc39ae1806fc6ba41e50a2d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397525"
---
# <a name="single-sign-on-event-10668"></a>シングル サインオン:イベント 10668
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                   エンタープライズ シングル サインオン                                                                                                                                                   |
| 製品バージョン |                                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                   |
|    イベント ID     |                                                                                                                                                             10668                                                                                                                                                             |
|  イベント ソース   |                                                                                                                                                            ENTSSO                                                                                                                                                             |
|    コンポーネント    |                                                                                                                                                              該当なし                                                                                                                                                              |
|  シンボル名  |                                                                                                                                               SSO_WARN_NO_OLD_WINDOWS_PASSWORD                                                                                                                                                |
|  メッセージ テキスト   | このアカウントの古い Windows パスワードが SSO database.%r で利用できないため、Windows パスワードを変更することはできません。<br /><br /> SSO 管理ツールを使用して、この Windows アカウントの外部資格情報を設定します。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> Windows アカウント: %3 |

## <a name="explanation"></a>説明  
 この警告イベントは、このアカウントの古い Windows パスワードが SSO データベースで利用できないために、パスワード同期が Windows パスワードを変更できないことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

-   このアダプター (イベント ログ メッセージ名) に割り当てられているどのアプリケーションを特定し、この Windows アカウントの外部資格情報を設定する SSO 管理ツールです。 それらのアプリケーションのすべてでは、(特定の Windows アカウント) の外部パスワードを設定する必要があります。  

## <a name="more-info"></a>詳細情報

- [パスワード同期](../core/password-synchronization2.md)  

- **パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
