---
title: シングル サインオン:イベント 10531 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 264941f4-7791-4a1f-a0bf-b992c9ccda64
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34767fb719ffe272720715ed1f4827979c9ff880
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262365"
---
# <a name="single-sign-on-event-10531"></a>シングル サインオン:イベント 10531
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                    エンタープライズ シングル サインオン                                                                                     |
| 製品バージョン |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                    |
|    イベント ID     |                                                                                              10531                                                                                               |
|  イベント ソース   |                                                                                              ENTSSO                                                                                              |
|    コンポーネント    |                                                                                               該当なし                                                                                                |
|  シンボル名  |                                                                                     SSO_ERROR_GET_SECRET_OK                                                                                      |
|  メッセージ テキスト   | マスター シークレット succeeded.%r を取得する要求<br /><br /> シークレット番号: % 1 %r<br /><br /> MSID: %2%r<br /><br /> クライアント ユーザー: % 3 %r<br /><br /> クライアント コンピューターの場合: % 4 %r<br /><br /> 追跡 ID: %5 |

## <a name="explanation"></a>説明  
 このイベントは、マスター シークレットに対する要求が成功したことを示します。  

## <a name="user-action"></a>ユーザーの操作  

- ユーザー操作は必要ありません。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)  

- [マスター シークレットの管理](../core/managing-the-master-secret.md)
