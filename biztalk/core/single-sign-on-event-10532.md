---
title: シングル サインオン:イベント 10532 |Microsoft Docs
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
ms.openlocfilehash: 3ea52d8e64f5a59a633a6e22eef7220f44b36f77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262338"
---
# <a name="single-sign-on-event-10532"></a>シングル サインオン:イベント 10532
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                              エンタープライズ シングル サインオン                                                                              |
| 製品バージョン |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                              |
|    イベント ID     |                                                                                        10532                                                                                        |
|  イベント ソース   |                                                                                       ENTSSO                                                                                        |
|    コンポーネント    |                                                                                         CO                                                                                          |
|  シンボル名  |                                                                             SSO_WARN_LOST_SECRET_SERVER                                                                             |
|  メッセージ テキスト   | マスター シークレットを取得できませんでした。 マスター シークレット サーバー名が正しいことおよび available.%r であることを確認します。<br /><br /> シークレット サーバー名: %1 %r<br /><br /> エラー コード: %2 |

## <a name="explanation"></a>説明  
 この警告イベントは、マスター シークレットを取得する要求が失敗したことを示します。 エンタープライズ シングル サインオン サービスがサーバーで実行されていない可能性があります。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の 1 つ以上の操作を行います。  

- アプリケーション イベント ログの関連するイベントまたはエラーを確認します。  

- マスター シークレット サーバー名が正しいことを確認します。  

- マスター シークレット サーバーがオンラインであり、エンタープライズ シングル サインオン サービスが実行されていることを確認します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)  

- [マスター シークレットの管理](../core/managing-the-master-secret.md)
