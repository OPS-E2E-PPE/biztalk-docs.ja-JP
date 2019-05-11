---
title: シングル サインオン:イベント 10678 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af92ce1-fdac-432f-be6b-cf8958aee776
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c8acb17f22b9b7fbf3faeaa918aa2fc0a7fd68e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397462"
---
# <a name="single-sign-on-event-10678"></a>シングル サインオン:イベント 10678
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                 |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                    エンタープライズ シングル サインオン                                                                                                                    |
| 製品バージョン |                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    イベント ID     |                                                                                                                              10678                                                                                                                              |
|  イベント ソース   |                                                                                                                             ENTSSO                                                                                                                              |
|    コンポーネント    |                                                                                                                               該当なし                                                                                                                               |
|  シンボル名  |                                                                                                                   SSO_WARN_PASSWORD_MISMATCH                                                                                                                    |
|  メッセージ テキスト   | 外部パスワード変更。 アダプターによって指定された古いパスワードが外部 account.%r の既存のパスワードと一致しません<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> 外部アカウント: %4 |

## <a name="explanation"></a>説明  
 この警告イベントは、アダプターによって指定された古いパスワードでは、外部アカウントの既存のパスワードが一致しないことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告は、次を解決するには。  

-   アダプター (イベント ログ メッセージ名) に割り当てられているどのアプリケーションを決定し、SSO 管理ツールを使用して、この外部アカウントの外部資格情報を設定します。 それらのアプリケーションのすべてでは、(特定のアカウント) の外部パスワードを設定する必要があります。  

## <a name="more-info"></a>詳細情報

- [パスワード同期](../core/password-synchronization2.md)  

- **パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
