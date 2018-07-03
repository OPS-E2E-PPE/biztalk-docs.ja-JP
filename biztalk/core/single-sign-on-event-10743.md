---
title: 'シングル サインオン: イベント 10743 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2908bc9-1fac-4ab9-869f-0c5512864da4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd0c8c170a17fade96daa0b9ecc0a3613afb1236
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003667"
---
# <a name="single-sign-on-event-10743"></a>シングル サインオン: イベント 10743
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                   エンタープライズ シングル サインオン                                                                    |
| 製品バージョン |                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                   |
|    イベント ID     |                                                                             10743                                                                              |
|  イベント ソース   |                                                                             ENTSSO                                                                             |
|    コンポーネント    |                                                                              N\A                                                                               |
|  シンボル名  |                                                                    SSO_ERROR_REPLAY_STOPPED                                                                    |
|  メッセージ テキスト   | 保存された外部パスワード変更の再生はエラーのため停止しました。%r<br /><br /> 再生ファイル: % 1 %r<br /><br /> 追加データ: % 2 %r<br /><br /> エラー コード: %3 |

## <a name="explanation"></a>説明  
 このエラー イベントは、保存された外部パスワード変更の再生がエラーのために停止したことを示します。  

 ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。 進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- 関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)
