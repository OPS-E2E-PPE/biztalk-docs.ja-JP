---
title: パブリック オーケストレーションなしに受信ポートをこの BizTalk アセンブリがある |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb901d49-ce3c-4bc6-806a-eb5964d32bb4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f4693321e02d0da6d8cec9b5ae1542fd62af6c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400541"
---
# <a name="there-are-no-orchestrations-with-public-receive-ports-in-this-biztalk-assembly"></a>この BizTalk アセンブリには、パブリック受信ポートを保持するオーケストレーションがありません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| 製品バージョン |                                                          [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                           |
|    イベント ID     |                                                                                       0                                                                                       |
|  イベント ソース   |                                                                                       0                                                                                       |
|    コンポーネント    |                                                                                       0                                                                                       |
|  シンボル名  |                                                                                       0                                                                                       |
|  メッセージ テキスト   | パブリック オーケストレーションなしに受信ポートをこの BizTalk アセンブリがあります。 [戻る] をクリックし、パブリックでオーケストレーションを含む BizTalk アセンブリを指定の受信ポート |
  
## <a name="explanation"></a>説明  
 このエラーは、選択したオーケストレーションには、パブリック ポートはありません。 ことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 パブリック ポートを構成するのにには、次の手順を使用します。  
  
#### <a name="to-configure-a-public-port"></a>パブリック ポートを構成するには  
  
1.  オーケストレーションを特定し、目的の受信ポートを公開します。  
  
    1.  ポート構成ウィザードを開きます。  
  
    2.  **ポートの種類を選択します。**、変更**アクセス制限**から**内部**(既定)**パブリック - 制限なし**します。  
  
2.  アセンブリを再コンパイルします。  
  
     \- または -  
  
     受信ポートをパブリックに BizTalk アセンブリを読み込みます。