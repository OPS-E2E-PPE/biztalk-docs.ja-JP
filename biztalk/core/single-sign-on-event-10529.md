---
title: シングル サインオン:イベント 10529 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75ed70e0-8458-4736-883f-a4536f094dc0
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 204e5d2ff2093b5980176d1696fd9bd45b892023
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262428"
---
# <a name="single-sign-on-event-10529"></a>シングル サインオン:イベント 10529
## <a name="details"></a>詳細  

|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                             エンタープライズ シングル サインオン                                             |
| 製品バージョン |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    イベント ID     |                                                       10529                                                       |
|  イベント ソース   |                                                      ENTSSO                                                       |
|    コンポーネント    |                                                        該当なし                                                        |
|  シンボル名  |                                            SSO_INFO_GOT_CURRENT_SECRET                                            |
|  メッセージ テキスト   | マスター シークレット server.%r から現在のシークレットを取得しました<br /><br /> シークレット サーバー名: %1 %r<br /><br /> MSID: %2 |

## <a name="explanation"></a>説明  
 この情報イベントは、SSO がマスター シークレット サーバーから要求されたマスター シークレットを示します。  

## <a name="user-action"></a>ユーザーの操作  

- ユーザー操作は必要ありません。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)  

- [マスター シークレットの管理](../core/managing-the-master-secret.md)
