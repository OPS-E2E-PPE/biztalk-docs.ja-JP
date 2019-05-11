---
title: BizTalkDTADb データベースのボトルネックを特定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4499bc3-d50b-4b97-b19c-93c7bcc40483
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44f506c58cd7aa2f82123fd397e3e010a7b6f557
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384980"
---
# <a name="how-to-identify-bottlenecks-in-the-biztalkdtadb-database"></a>BizTalkDTADb データベースのボトルネックを特定する方法
BizTalkDTADb データベースのボトルネックを特定するには、次の手順を実行します。  
  
1.  SQL エージェント サービスが実行されていることを確認します。  
  
2.  Archive/Purge ジョブが実行され、正常に完了することを確認します。  
  
3.  DTADb アーカイブとデータベース サイズの増加に対応できるだけの十分な空きディスク領域があることを確認します。