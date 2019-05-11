---
title: シングル サインオン:イベント 10681 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87ce2e50-cf54-4b23-b247-f137ce64ba1d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf8f6edaf7f524984365ffcca35ead803fa0693c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397424"
---
# <a name="single-sign-on-event-10681"></a>シングル サインオン:イベント 10681
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                              エンタープライズ シングル サインオン                                                                                               |
| 製品バージョン |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                              |
|    イベント ID     |                                                                                                        10681                                                                                                         |
|  イベント ソース   |                                                                                                        ENTSSO                                                                                                        |
|    コンポーネント    |                                                                                                         該当なし                                                                                                          |
|  シンボル名  |                                                                                         SSO_WARN_NO_WINDOWS_PASSWORD_CHANGE                                                                                          |
|  メッセージ テキスト   | 外部パスワード変更。 1 つ以上の外部アカウント failed.%r が変更されるため、Windows パスワードは変更されませんでした。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> Windows アカウント: %3 |

## <a name="explanation"></a>説明  
 この警告イベントは、1 つまたは複数の外部アカウントの変更が失敗したため、Windows パスワードが変更しないことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の 1 つ以上の操作を行います。  

-   関連するイベントのシステムおよびアプリケーション イベント ログを確認します。  

-   SSO 管理ツールを使用してアダプター構成を確認します。  

-   外部システムを確認します。  

## <a name="more-info"></a>詳細情報

- [パスワード同期](../core/password-synchronization2.md)  

- **パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
