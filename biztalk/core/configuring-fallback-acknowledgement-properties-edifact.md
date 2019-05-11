---
title: フォールバック受信確認プロパティ (EDIFACT) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6062b881-3214-4e68-acbc-1f8c255fd86b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75545d752e531c603e7e7e04fee8bda311b6f1a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355818"
---
# <a name="configuring-fallback-acknowledgement-properties-edifact"></a>フォールバック受信確認プロパティ (EDIFACT) の構成
フォールバック アグリーメントでは、パーティに返す受信確認の種類を指定できます。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-edifact-ack-contrl-properties"></a>EDIFACT 確認 (CONTRL) プロパティを構成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**EDIFACT フォールバックの設定**します。  
  
2. **EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[ **受信確認**します。  
  
3. 選択**メッセージの受信 (CONTRL が必要です)** をインターチェンジの送信者に技術確認 (CONTRL) を返します。  
  
4. 選択**確認 (CONTRL) が必要です**をインターチェンジの送信者に機能確認 (CONTRL) を返します。  
  
5. をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジ処理に対する EDIFACT フォールバック アグリーメント プロパティの構成](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)