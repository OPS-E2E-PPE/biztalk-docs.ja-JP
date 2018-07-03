---
title: 'シングル サインオン: イベント 10531 |Microsoft Docs'
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
ms.openlocfilehash: 74dd7f4e39997e3bbd78ffce8a7bd164968bb358
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006763"
---
# <a name="single-sign-on-event-10531"></a>シングル サインオン: イベント 10531
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                    エンタープライズ シングル サインオン                                                                                     |
| 製品バージョン |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                    |
|    イベント ID     |                                                                                              10531                                                                                               |
|  イベント ソース   |                                                                                              ENTSSO                                                                                              |
|    コンポーネント    |                                                                                               N\A                                                                                                |
|  シンボル名  |                                                                                     SSO_ERROR_GET_SECRET_OK                                                                                      |
|  メッセージ テキスト   | マスター シークレットの取得要求が正常に完了しました。%r<br /><br /> シークレット番号: % 1 %r<br /><br /> MSID: % 2 %r<br /><br /> クライアント ユーザー: % 3 %r<br /><br /> クライアント コンピューターの場合: % 4 %r<br /><br /> 追跡 ID: %5 |

## <a name="explanation"></a>説明  
 このイベントは、マスター シークレットに対する要求が正常に完了したことを示します。  

## <a name="user-action"></a>ユーザーの操作  

- ユーザーの操作は必要ありません。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)  

- [マスター シークレットの管理](../core/managing-the-master-secret.md)
