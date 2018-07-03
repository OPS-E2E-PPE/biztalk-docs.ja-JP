---
title: 'シングル サインオン: イベント 10532 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae2112bc-b53c-4d99-9dc1-a2f55dda4665
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 135060013686ff24e4f2692bda0e8829189e1c4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974851"
---
# <a name="single-sign-on-event-10532"></a>シングル サインオン: イベント 10532
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                              エンタープライズ シングル サインオン                                                                              |
| 製品バージョン |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                              |
|    イベント ID     |                                                                                        10532                                                                                        |
|  イベント ソース   |                                                                                       ENTSSO                                                                                        |
|    コンポーネント    |                                                                                         CO                                                                                          |
|  シンボル名  |                                                                             SSO_WARN_LOST_SECRET_SERVER                                                                             |
|  メッセージ テキスト   | マスター シークレットを取得できませんでした。 マスター シークレット サーバー名が正しいこと、および利用可能であることを確認してください。%r<br /><br /> シークレット サーバー名: %1 %r<br /><br /> エラー コード: %2 |

## <a name="explanation"></a>説明  
 この警告イベントは、マスター シークレットの取得要求が失敗したことを示します。 エンタープライズ シングル サインオン サービスがサーバー上で実行されていないことが原因である可能性があります。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の操作を行います:   

- 関連するイベントまたはエラーについては、アプリケーション イベント ログを確認します。  

- マスター シークレット サーバー名が正しいことを確認します。  

- マスター シークレット サーバーがオンラインであり、エンタープライズ シングル サインオン サービスが実行されていることを確認します。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)  

- [マスター シークレットの管理](../core/managing-the-master-secret.md)
