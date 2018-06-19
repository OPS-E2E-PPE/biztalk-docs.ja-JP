---
title: メッセージの署名に使用される証明書がローカル証明書ストアにある |Microsoft ドキュメント
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
ms.openlocfilehash: d94049a0ecca4e7aec89c5163231c0b9bf4c9e3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239962"
---
# <a name="the-certificate-used-for-signing-a-message-cannot-be-located-in-the-local-certificate-store"></a>メッセージの署名に使用される証明書を、ローカルの証明書ストアに配置できません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|CertificateMissingError|  
|メッセージ テキスト|メッセージの署名に使用される証明書を、ローカルの証明書ストアに配置できません。 証明書の拇印: {0}|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、署名証明書として識別された証明書が要求された証明書ストアになかったため、送信パイプラインで送信メッセージを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  
  
1.  BizTalk Server 管理コンソールを開いて署名証明書を特定し、[BizTalk グループ] を右クリックして、[証明書] ノードをクリックします。  
  
2.  MMC を開き、[ユーザー アカウント] のスナップインを追加して、[証明書] ノード、[個人] ノード、[証明書] ノードの順に開きます。  
  
3.  エラー メッセージ テキストに示された拇印を検索し、現在のユーザーの証明書ストアにその署名証明書の秘密キーが含まれていることを確認します。