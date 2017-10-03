---
title: "パーティの解決用の証明書を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 060101c1-14f3-4600-a18e-48a160d59bca
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 153c8ccce1fafbe32c51b1c048fad4081f5b0b0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-certificates-for-party-resolution"></a>パーティの解決用の証明書を構成する方法
BizTalk エクスプ ローラーを使用してパーティを構成するときに、そのデジタル署名を使用してパーティを解決できるように、パーティを構成できます。 これにより、パーティを構成する場合と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がメッセージを受信メッセージの送信者を判断し、送信者の既知のパーティを解決するは、公開キー証明書を使用、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行する必要がありますログインする必要がのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  
  
### <a name="to-configure-party-resolution-to-use-a-certificate"></a>証明書を使用するパーティの解決を構成するには  
  
1.  開く、**パーティ プロパティ** ダイアログ ボックス。  
  
2.  クリックして、**証明書** タブをクリックして**参照**です。  
  
3.  証明書を選択します。  
  
4.  **[OK]**をクリックします。