---
title: シングル サインオン:イベント 10547 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be25cdc9-d6c1-488d-9ead-877a2454c3d1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8ec8133a6d2456e2cdafca56ae956f6be1d31a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243423"
---
# <a name="single-sign-on-event-10547"></a>シングル サインオン:イベント 10547
## <a name="details"></a>詳細  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  製品名   |                         エンタープライズ シングル サインオン                         |
| 製品バージョン |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    イベント ID     |                                   10547                                   |
|  イベント ソース   |                                  ENTSSO                                   |
|    コンポーネント    |                                    CO                                     |
|  シンボル名  |                          SSO_WARN_UPDATE_FAILED                           |
|  メッセージ テキスト   | 再暗号化中に、SSO データベース内の資格情報を更新できませんでした。 |

## <a name="explanation"></a>説明  
 この警告イベントは、新しい暗号化の結果で資格情報を更新することがないことを示します。 新しいシークレットを生成することによって、または古いシークレットを復元することで、マスター シークレットが変更されたときに、再暗号化は、以前のシークレットで暗号化されたすべてのシークレットの暗号化解除し、再暗号化して、新しいシークレットを SSO データベースで実行されます。 このイベントは、再暗号化の過程で、資格情報が削除された場合に発生することができます。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

- 別の再暗号化に若干の遅延の後に発生するまで待ちます自動的を実行しない場合は、1 つが必要な場合に、新しい再暗号化をトリガーする SSO サービスを再起動します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [SSO について](../core/understanding-sso.md)
