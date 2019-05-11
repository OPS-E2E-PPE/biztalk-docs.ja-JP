---
title: シングル サインオン:イベント 10536 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d493a45b-c4ed-40fc-8803-b3ca12f9795b
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b66b9a37a92614b10849ac39bd8385d9e850efb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262238"
---
# <a name="single-sign-on-event-10536"></a>シングル サインオン:イベント 10536
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                     エンタープライズ シングル サインオン                                                                                      |
| 製品バージョン |                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                     |
|    イベント ID     |                                                                                               10536                                                                                                |
|  イベント ソース   |                                                                                               ENTSSO                                                                                               |
|    コンポーネント    |                                                                                                 CO                                                                                                 |
|  シンボル名  |                                                                                         SSO_WARN_API_AUDIT                                                                                         |
|  メッセージ テキスト   | SSO の監査 %r<br /><br /> 関数: %1 %r<br /><br /> 追跡 ID: %2 %r<br /><br /> クライアント コンピューターの場合: % 3 %r<br /><br /> クライアント ユーザー: % 4 %r<br /><br /> アプリケーション名: % 5% の r<br /><br /> エラー コード: %6 |

## <a name="explanation"></a>説明  
 この警告監査イベントは、ユーザー定義の監査レベルを満たすイベントが発生したことを示します。 このイベント メッセージは次のとおりです。  

 **関数:** 実行中の関数します。  

 **追跡 ID:** SSO API が初めて呼び出されたときに生成される一意の GUID。  

 **クライアント コンピューターの場合:** クライアント コンピューターが、関数が発信元であります。  

 **クライアント ユーザー:** 関数を呼び出したユーザー アカウントの名前。  

 **アプリケーション名:** SSO の名前には、この関数に関連付けられたアプリケーションが関連します。  

 **エラー コード:** エラーの一意の識別子です。  

 この種類のイベントは、開発中に問題を診断、トラブルシューティング、またはアプリケーションの実行に使用されます。 SSO API 呼び出しが行われるを決定する提供情報を使用できます。  

 監査レベルを設定することが 0 では 0/1/2/3 – には"none"、1 は「低」には、エラーのみが表示されます、2 は「中」の表示エラーと警告、および 3 はすべての監査メッセージを「高」が表示されます。  

## <a name="user-action"></a>ユーザーの操作  

- 関連するイベント メッセージは、イベント ログを確認します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [SSO を監査する方法](../core/how-to-audit-sso.md)  

- [SSO の使用](../core/using-sso.md)
