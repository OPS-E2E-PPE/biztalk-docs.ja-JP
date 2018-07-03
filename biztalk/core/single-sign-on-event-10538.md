---
title: 'シングル サインオン: イベント 10538 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1211ac33-9149-4dd3-85a2-d46eb24d1060
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f4b7fba63d26fde664e14470eb95b41a1580ae7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975779"
---
# <a name="single-sign-on-event-10538"></a>シングル サインオン: イベント 10538
## <a name="details"></a>詳細  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  製品名   |                         エンタープライズ シングル サインオン                         |
| 製品バージョン |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    イベント ID     |                                   10538                                   |
|  イベント ソース   |                                  ENTSSO                                   |
|    コンポーネント    |                                    CO                                     |
|  シンボル名  |                           SSO_WARN_APP_DISABLED                           |
|  メッセージ テキスト   | このアプリケーションは現在無効になっています。%r<br /><br /> アプリケーション名: %1 |

## <a name="explanation"></a>説明  
 この警告イベントは、アプリケーション管理者が SSO 関連アプリケーションを無効にしていることを示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の操作を行います:   

- アプリケーション管理者に問い合わせて、SSO 関連アプリケーションを有効にします。 SSO 管理ツール (GUI またはコマンド ライン) を使用して行うことができます。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md)  

- [関連アプリケーションを無効にする方法](../core/how-to-disable-an-affiliate-application.md)
