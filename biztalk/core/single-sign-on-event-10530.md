---
title: シングル サインオン:イベント 10530 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bb37305-26fe-46a7-958d-3ed7f6876a7b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccdea8c120bba407f22f24f28afd425768ff24b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262396"
---
# <a name="single-sign-on-event-10530"></a>シングル サインオン:イベント 10530
## <a name="details"></a>詳細  

|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                             エンタープライズ シングル サインオン                                              |
| 製品バージョン |                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    イベント ID     |                                                       10530                                                        |
|  イベント ソース   |                                                       ENTSSO                                                       |
|    コンポーネント    |                                                        該当なし                                                         |
|  シンボル名  |                                            SSO_INFO_GOT_PREVIOUS_SECRET                                            |
|  メッセージ テキスト   | マスター シークレット server.%r から以前のシークレットを取得しました<br /><br /> シークレット サーバー名: %1 %r<br /><br /> MSID: %2 |

## <a name="explanation"></a>説明  
 この情報イベントは、SSO が以前のマスター シークレットを持つことを示します。  

## <a name="user-action"></a>ユーザーの操作  

- ユーザー操作は必要ありません。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)  

- [マスター シークレットの管理](../core/managing-the-master-secret.md)
