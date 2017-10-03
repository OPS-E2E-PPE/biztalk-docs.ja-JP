---
title: "フォールバック受信確認プロパティ (EDIFACT) の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6062b881-3214-4e68-acbc-1f8c255fd86b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d9369eb7fff1a6217da774aaf62af6e036d0abd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-acknowledgement-properties-edifact"></a>フォールバック受信確認プロパティを構成する (EDIFACT)
フォールバック アグリーメントでは、パーティに返す受信確認の種類を指定できます。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-edifact-ack-contrl-properties"></a>EDIFACT 確認 (CONTRL) プロパティを構成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**パーティ**ノードをクリックして**EDIFACT フォールバックの設定**です。  
  
2.  **EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[ **受信確認**です。  
  
3.  選択**メッセージの受信 (CONTRL が必要です)**をインターチェンジ送信者に技術 (CONTRL) 確認を返します。  
  
4.  選択**確認 (CONTRL) が必要です**をインターチェンジ送信者に機能 (CONTRL) 確認を返します。  
  
5.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジ処理に対する EDIFACT フォールバック アグリーメントのプロパティを構成します。](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)