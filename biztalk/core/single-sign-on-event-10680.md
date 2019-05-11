---
title: シングル サインオン:イベント 10680 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88ea12ff-d181-423f-9054-b0c656cc4558
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a8b734006a8ec0181a3307386a32d8d249eaa25
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397433"
---
# <a name="single-sign-on-event-10680"></a>シングル サインオン:イベント 10680
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                        エンタープライズ シングル サインオン                                                                                                                                        |
| 製品バージョン |                                                                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                        |
|    イベント ID     |                                                                                                                                                  10680                                                                                                                                                  |
|  イベント ソース   |                                                                                                                                                 ENTSSO                                                                                                                                                  |
|    コンポーネント    |                                                                                                                                                   該当なし                                                                                                                                                   |
|  シンボル名  |                                                                                                                                      SSO_WARN_PS_GET_CREDS_FAILED                                                                                                                                       |
|  メッセージ テキスト   | 既存の外部資格情報を SSO database.%r から取得できませんでした。 ので、外部アカウントのパスワードが変更されませんでした。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> 外部アカウント: % 4 %r<br /><br /> エラー コード: %5 |

## <a name="explanation"></a>説明  
 この警告イベントは、パスワードが変更されていないこと、外部アカウントの既存の外部資格情報を SSO データベースから取得できませんでしたのでを示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

-   外部資格情報を確認します。  

-   外部資格情報が有効でない、SSO 管理ツールを使用して、この外部アカウントの外部資格情報を設定します。 関連付けられているすべてのアプリケーションでは、(特定のアカウント) の外部パスワードを設定する必要があります。  

## <a name="more-info"></a>詳細情報

- [パスワード同期](../core/password-synchronization2.md)  

- **パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
