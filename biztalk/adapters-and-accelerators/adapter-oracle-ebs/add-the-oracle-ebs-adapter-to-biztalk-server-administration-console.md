---
title: Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加します |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24b126aa-2a05-49fa-80e1-f1d5c21ad60f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b11a6959ecffb7447c577153104977bd90815105
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375811"
---
# <a name="add-the-oracle-e-business-suite-adapter-to-biztalk-server-administration-console"></a>Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加します。
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] BizTalk Server で WCF カスタム ポートまたは Wcf-oracleebs ポートとして使用できます。 使用する場合、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF カスタム ポートには WCF カスタム ポートを追加する必要はありません、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに、WCF カスタム ポートが追加されるため、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]既定では、管理コンソール。 ただし、使用する場合、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Wcf-oracleebs ポートを経由する Wcf-oracleebs アダプターを最初に追加する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
 このトピックでは、Wcf-oracleebs アダプターを追加する方法を手順については、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
> [!IMPORTANT]
>  WCF カスタム ポートを構成するかどうか、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、この手順を実行する必要はありません。  
  
### <a name="to-add-the-oracle-e-business-suite-adapter"></a>Oracle E-business Suite アダプターを追加するには  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. コンソール ツリーで、展開、 **BizTalk グループ**、展開**プラットフォームの設定**、 をクリックし、**アダプター**します。  
  
3. 右クリックして**アダプター**、 をポイント**新規**、 をクリック**アダプター**します。  
  
    ![アダプターを追加する](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4. **アダプター プロパティ**] ダイアログ ボックスで、アダプターとの間の名前を指定します、**アダプター**一覧で、[ **Wcf-oracleebs**します。  
  
    ![WCF の追加&#45;OracleEBS BizTalk アダプター](../../adapters-and-accelerators/adapter-oracle-ebs/media/3e2cde5a-9f32-489c-a931-0dd509451e62.gif "3e2cde5a-9f32-489c-a931-0dd509451e62")  
  
5. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [Oracle E-business Suite のアプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)