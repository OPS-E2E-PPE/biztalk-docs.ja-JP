---
title: シングル サインオン:イベント 10666 |Microsoft Docs
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
ms.openlocfilehash: 921f11f422e4707d81a9387cd9606c3dfd3f337d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397545"
---
# <a name="single-sign-on-event-10666"></a>シングル サインオン:イベント 10666
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                         エンタープライズ シングル サインオン                                                                          |
| 製品バージョン |                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                         |
|    イベント ID     |                                                                                   10666                                                                                    |
|  イベント ソース   |                                                                                   ENTSSO                                                                                   |
|    コンポーネント    |                                                                                    該当なし                                                                                     |
|  シンボル名  |                                                                  SSO_INFO_DAMPED_EXTERNAL_PASSWORD_CHANGE                                                                  |
|  メッセージ テキスト   | 外部パスワード変更は抑制されました (重複および discarded).%r として検出します。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> 外部アカウント: %3 |

## <a name="explanation"></a>説明  
 この情報イベントは、外部パスワード変更が重複するいると判断して、破棄されることを示します。  

## <a name="user-action"></a>ユーザーの操作  

- ユーザー操作は必要ありません。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [パスワード同期](../core/password-synchronization2.md)
