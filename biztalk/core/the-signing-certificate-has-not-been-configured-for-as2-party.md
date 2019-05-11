---
title: AS2 パーティの署名証明書が構成されていません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82928a39-3acf-447b-a0e8-f7c25b6f38dc
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 695c2d8ef697ea3cddbdc72880a844e4ece7a8c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292920"
---
# <a name="the-signing-certificate-has-not-been-configured-for-as2-party"></a>AS2 パーティの署名証明書が構成されていません
## <a name="details"></a>詳細  
  
|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  製品名   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]     |
| 製品バージョン |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                 |
|    イベント ID     |                                             -                                             |
|  イベント ソース   |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI   |
|    コンポーネント    |                                        AS2 エンジン                                         |
|  シンボル名  |                               SigningCertNotConfiguredError                               |
|  メッセージ テキスト   | AS2 パーティの署名証明書が構成されていません。  AS2-から。{0} AS2 にします。 {1} |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、グループの署名証明書が構成されていなかったためにで、送信メッセージが送信パイプラインでした処理することを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の手順で署名証明書を構成します。  
  
1.  BizTalk Server 管理コンソールを開きます。  
  
2.  グループ ノードに移動し、証明書 ノードをクリックします。  
  
3.  共通名と証明書の拇印を入力します。