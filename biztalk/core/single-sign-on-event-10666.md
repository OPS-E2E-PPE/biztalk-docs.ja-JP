---
title: 'シングル サインオン: イベント 10666 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 103947bb-e843-4427-a28a-1cceec90e2ae
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a82308e721f53f9d4eb81fdbdad771b69a1cade5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018272"
---
# <a name="single-sign-on-event-10666"></a>シングル サインオン: イベント 10666
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                         エンタープライズ シングル サインオン                                                                          |
| 製品バージョン |                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                         |
|    イベント ID     |                                                                                   10666                                                                                    |
|  イベント ソース   |                                                                                   ENTSSO                                                                                   |
|    コンポーネント    |                                                                                    N\A                                                                                     |
|  シンボル名  |                                                                  SSO_INFO_DAMPED_EXTERNAL_PASSWORD_CHANGE                                                                  |
|  メッセージ テキスト   | 外部パスワードの変更は抑制されました (重複として検出され、破棄されました)。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> 外部アカウント: %3 |

## <a name="explanation"></a>説明  
 この情報イベントは、外部パスワードの変更が重複していると判断され、破棄されたことを示します。  

## <a name="user-action"></a>ユーザーの操作  

- ユーザーの操作は必要ありません。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [パスワード同期](../core/password-synchronization2.md)
