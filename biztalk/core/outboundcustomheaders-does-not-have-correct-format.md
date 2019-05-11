---
title: OutboundCustomHeaders は正しい形式をありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6097762b-01c9-48b8-8cee-ccd6b11d28d4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db856038267ff6c8472f85e1a9b87a389a1d8047
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393445"
---
# <a name="outboundcustomheaders-does-not-have-correct-format"></a>OutboundCustomHeaders には、正しい形式はありません。
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                OutboundCustomHeaders には、正しい形式はありません。                |
  
## <a name="explanation"></a>説明  
 WCF の値。InboundHeaders または WCF です。OutboundCustomHeaders は次の形式がありません:\<ヘッダー\>...\</headers\>します。  
  
## <a name="user-action"></a>ユーザーの操作  
 プロパティ値をラップ\<ヘッダー\>要素。  
  
 詳細についてで、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
-   [パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーの使用](../core/using-soap-headers-in-wcf-messages-with-pipeline-components.md)