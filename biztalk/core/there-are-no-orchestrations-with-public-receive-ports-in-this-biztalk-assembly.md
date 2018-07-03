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
ms.openlocfilehash: c062f5e23972ed841c4c9d614ad58967a07a4fe2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978217"
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
|  メッセージ テキスト   | この BizTalk アセンブリには、パブリック受信ポートを保持するオーケストレーションがありません。 [戻る] をクリックして、パブリック受信ポートを保持するオーケストレーションを含む BizTalk アセンブリを指定してください。 |
  
## <a name="explanation"></a>説明  
 このエラーは、選択したオーケストレーションにパブリック ポートがないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 パブリック ポートを構成するには、次の手順を実行します。  
  
#### <a name="to-configure-a-public-port"></a>パブリック ポートを構成するには  
  
1.  オーケストレーションを特定し、目的の受信ポートをパブリックにします。  
  
    1.  ポート構成ウィザードを開きます。  
  
    2.  **ポートの種類を選択します。**、変更**アクセス制限**から**内部**(既定)**パブリック - 制限なし**します。  
  
2.  アセンブリを再コンパイルします。  
  
     \- または -  
  
     パブリック受信ポートがある BizTalk アセンブリを読み込みます。