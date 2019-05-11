---
title: シングル サインオン:イベント 10709 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98e86890-88dd-49f0-bb2c-1234507e8be5
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4f69e2226ab304e9d6b23ead1c9e2b84ffa9fb4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397244"
---
# <a name="single-sign-on-event-10709"></a>シングル サインオン:イベント 10709
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                  エンタープライズ シングル サインオン                                                                                                                   |
| 製品バージョン |                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                  |
|    イベント ID     |                                                                                                                            10709                                                                                                                             |
|  イベント ソース   |                                                                                                                            ENTSSO                                                                                                                            |
|    コンポーネント    |                                                                                                                             該当なし                                                                                                                              |
|  シンボル名  |                                                                                                                SSO_WARN_PS_PCNS_ACCESS_DENIED                                                                                                                |
|  メッセージ テキスト   | アクセス domain.%r 内に、PCNS から Windows パスワード変更がドメイン コント ローラーから受け入れのみ<br /><br /> 追跡 ID: %1 %r<br /><br /> クライアント ユーザー: % 2 %r<br /><br /> アクセス ドメイン: % 3 %r<br /><br /> アクセス Sid: % 4 %r<br /><br /> エラー コード: %5 |

## <a name="explanation"></a>説明  
 この警告イベントでは、Windows パスワードの変更が、ENTSSO サーバーのドメインの外部のサーバーでパスワード変更通知サービス (PCNS) からを受信したことを示します。 Windows パスワードの変更は、ENTSSO サーバーと同じドメインのドメイン コント ローラーからのみ受け付けられます。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

- PCNS と同じドメイン内には、ENTSSO サーバーを構成します。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期](../core/password-synchronization2.md)
