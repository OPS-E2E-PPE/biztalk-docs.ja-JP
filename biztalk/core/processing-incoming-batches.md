---
title: "受信バッチの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98f47903-933a-4bde-b320-f7689c3d8366
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca3781d9b7c1ed2190a8334f272c04d304669ace
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="processing-incoming-batches"></a>受信バッチの処理
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がバッチ EDI インターチェンジを受信したときは、インターチェンジを複数のトランザクション セットに分割して各セットを個別に処理するか、インターチェンジをそのまま保持してすべてのトランザクション セットを 1 つのグループとして処理することができます。  
  
 バッチ処理を決定する、**ローカル ホスト設定**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックスの X12 と EDIFACT の両方のアグリーメント。 インターチェンジをそのまま保持する場合は、エラーの発生時にインターチェンジまたはトランザクション セットを保留するかどうかを選択できます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [バッチ EDI インターチェンジの分割](../core/splitting-a-batched-edi-interchange.md)  
  
-   [HIPAA サブドキュメントの分割](../core/splitting-hipaa-subdocuments.md)  
  
-   [バッチ EDI インターチェンジを受信した保持](../core/preserving-a-received-batched-edi-interchange.md)