---
title: フォールバック受信確認プロパティ (X12) の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce33f5dd-fbd5-448c-8ea3-05dd1467131a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 216961dea0bdf4a67c550fba8a599eff2d0c89ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232834"
---
# <a name="configuring-fallback-acknowledgement-properties-x12"></a>フォールバック受信確認プロパティの構成 (X12)
フォールバック アグリーメントでは、パーティから受信した X12 エンコード インターチェンジへの応答としての受信確認を [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で生成する方法、およびパーティに返す受信確認の種類を指定できます。 ここでは、この指定を行う手順について説明します。  
  
> [!NOTE]
>  ここで説明する受信確認プロパティは、HIPAA の受信確認にも適用されます。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-x12-ack-properties"></a>X12 確認のプロパティを構成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノードをクリックして**X12 フォールバック設定**です。  
  
2.  **X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[ **受信確認**.  
  
3.  選択**TA1 が必要**をインターチェンジ送信者に技術 (TA1) 確認を返します。  
  
4.  選択**997 が必要**をインターチェンジ送信者に機能 (997) 確認を返します。  
  
5.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [設定の X12 インターチェンジ処理のためのフォールバック アグリーメント プロパティ](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)