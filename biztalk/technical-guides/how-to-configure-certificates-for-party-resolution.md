---
title: パーティの解決用の証明書を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 060101c1-14f3-4600-a18e-48a160d59bca
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad5a25799599c668011e9ef2e322a016f649b198
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253493"
---
# <a name="how-to-configure-certificates-for-party-resolution"></a>パーティの解決用の証明書を構成する方法
BizTalk エクスプ ローラーを使用してパーティを構成する場合は、デジタル署名を使用して、パーティが解決されるように、パーティを構成できます。 この方法で、パーティを構成する場合と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がメッセージを受信メッセージの送信者を判断し、送信者に既知のパーティに解決には公開キー証明書を使用、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行する必要がありますがログオンしてのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  
  
### <a name="to-configure-party-resolution-to-use-a-certificate"></a>証明書を使用するパーティの解決を構成するには  
  
1.  開く、**パーティ プロパティ** ダイアログ ボックス。  
  
2.  をクリックして、**証明書**タブをクリックし、をクリックし、**参照**します。  
  
3.  証明書を選択します。  
  
4.  **[OK]** をクリックします。