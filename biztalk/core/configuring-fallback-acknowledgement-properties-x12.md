---
title: フォールバック受信確認プロパティ (X12) の構成 |Microsoft Docs
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
ms.openlocfilehash: 26ba465598f94f5f9ff41e74d50962a71b0ad979
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391255"
---
# <a name="configuring-fallback-acknowledgement-properties-x12"></a>フォールバック受信確認プロパティの構成 (X12)
フォールバック アグリーメントで指定できますか[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パーティとパーティに返す受信確認の種類から受信した X12 エンコード インターチェンジへの応答の受信確認を生成します。 このセクションでは、同じ操作を実行する方法の手順を提供します。  
  
> [!NOTE]
>  ここで説明する受信確認プロパティは、HIPAA の受信確認にも適用されます。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-x12-ack-properties"></a>X12 確認のプロパティを構成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**X12 フォールバックの設定**します。  
  
2. **X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[ **受信確認**.  
  
3. 選択**TA1 が必要**をインターチェンジの送信者に技術 (TA1) 確認を返します。  
  
4. 選択**997 が必要**機能 (997) 確認をインターチェンジの送信者に戻ります。  
  
5. をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジ処理用の X12 フォールバック アグリーメント プロパティの構成](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)