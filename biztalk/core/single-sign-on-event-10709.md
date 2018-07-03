---
title: 'シングル サインオン: イベント 10709 |Microsoft Docs'
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
ms.openlocfilehash: b114b8afb55c41171ef537a9dfc56d341943a226
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014251"
---
# <a name="single-sign-on-event-10709"></a>シングル サインオン: イベント 10709
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                  エンタープライズ シングル サインオン                                                                                                                   |
| 製品バージョン |                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                  |
|    イベント ID     |                                                                                                                            10709                                                                                                                             |
|  イベント ソース   |                                                                                                                            ENTSSO                                                                                                                            |
|    コンポーネント    |                                                                                                                             N\A                                                                                                                              |
|  シンボル名  |                                                                                                                SSO_WARN_PS_PCNS_ACCESS_DENIED                                                                                                                |
|  メッセージ テキスト   | PCNS からの Windows パスワード変更は、アクセス ドメイン内のドメイン コントローラーからのみ受け付けられます。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> クライアント ユーザー: % 2 %r<br /><br /> アクセス ドメイン: % 3 %r<br /><br /> アクセス Sid: % 4 %r<br /><br /> エラー コード: %5 |

## <a name="explanation"></a>説明  
 この警告イベントは、Windows パスワード変更が、ENTSSO サーバーのドメイン以外のサーバー上のパスワード変更通知サービス (PCNS) から受信されたことを示します。 Windows パスワード変更は、ENTSSO サーバーと同じドメイン内のドメイン コントローラーからのみ受け付けられます。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   

- PCNS と同じドメイン内で ENTSSO サーバーを構成します。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期](../core/password-synchronization2.md)
