---
title: 'シングル サインオン: イベント 10535 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b570b0b-5c45-4be3-80c9-a2c50601b677
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e075adb07b42194d8ea502c4ad50d9ebd47663b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023896"
---
# <a name="single-sign-on-event-10535"></a>シングル サインオン: イベント 10535
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                       エンタープライズ シングル サインオン                                                                       |
| 製品バージョン |                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                       |
|    イベント ID     |                                                                                 10535                                                                                 |
|  イベント ソース   |                                                                                ENTSSO                                                                                 |
|    コンポーネント    |                                                                                  CO                                                                                   |
|  シンボル名  |                                                                          SSO_INFO_API_AUDIT                                                                           |
|  メッセージ テキスト   | SSO の監査%r<br /><br /> 関数: %1 %r<br /><br /> 追跡 ID: %2 %r<br /><br /> クライアント コンピューターの場合: % 3 %r<br /><br /> クライアント ユーザー: % 4 %r<br /><br /> アプリケーション名: %5 |

## <a name="explanation"></a>説明  
 この情報監査イベントは、ユーザー定義の監査レベルを満たすイベントが発生したことを示します。 このイベント メッセージには次の項目が含まれます。  

 **関数:** 関数が実行されています。  

 **追跡 ID:** SSO API が最初に生成された一意の GUID が呼び出されます。  

 **クライアント コンピューターの場合:** 関数が作成されたクライアント コンピューター。  

 **クライアント ユーザー:** 関数を呼び出したユーザー アカウントの名前。  

 **アプリケーション名:** 関連のこの関数に関連付けられているアプリケーションを SSO の名前。  

 この種類のイベントは、開発、トラブルシューティング、またはアプリケーションの実行時に発生した問題の診断に使用されます。 表示された情報を使用して、実行中の SSO API 呼び出しを判別できます。  

 監査レベルは 0/1/2/3 に設定できます。0 は “オフ”、1 は “低“ でエラーのみが表示され、2 は “中” でエラーと警告が表示され、3 は “高” ですべての監査メッセージが表示されます。  

## <a name="user-action"></a>ユーザーの操作  

- 関連するイベント メッセージについては、イベント ログを確認します。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [SSO を監査する方法](../core/how-to-audit-sso.md)  

- [SSO の使用](../core/using-sso.md)
