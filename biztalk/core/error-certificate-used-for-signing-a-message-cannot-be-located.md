---
title: メッセージの署名に使用する証明書は、ローカル証明書ストアにあることはできません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ff3c7a2-954c-4c62-a7b2-06f7a38d61b3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f452ff362a11a824f749fc1a9c87b0905340c467
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348963"
---
# <a name="the-certificate-used-for-signing-a-message-cannot-be-located-in-the-local-certificate-store"></a>メッセージの署名に使用する証明書は、ローカル証明書ストアにあることはできません。
## <a name="details"></a>詳細  
  
|                 |                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                    |
| 製品バージョン |                                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                |
|    イベント ID     |                                                            -                                                             |
|  イベント ソース   |                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                  |
|    コンポーネント    |                                                        AS2 エンジン                                                        |
|  シンボル名  |                                                 CertificateMissingError                                                  |
|  メッセージ テキスト   | メッセージの署名に使用される証明書を、ローカルの証明書ストアに配置できません。 証明書の拇印: {0} |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、署名証明書として識別された証明書が要求された証明書ストアになかったため、送信パイプラインで送信メッセージを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  
  
1.  BizTalk Server 管理コンソールを開いて署名証明書を特定し、[BizTalk グループ] を右クリックして、[証明書] ノードをクリックします。  
  
2.  MMC を開き、[ユーザー アカウント] のスナップインを追加して、[証明書] ノード、[個人] ノード、[証明書] ノードの順に開きます。  
  
3.  エラー メッセージ テキストに示された拇印を検索し、現在のユーザーの証明書ストアにその署名証明書の秘密キーが含まれていることを確認します。