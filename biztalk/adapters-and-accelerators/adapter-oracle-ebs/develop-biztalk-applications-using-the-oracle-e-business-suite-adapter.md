---
title: Oracle E-business Suite アダプターを使用して BizTalk アプリケーションの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf3374a2-2fca-4df4-a1b1-d11cdc05d393
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ecbd7fd418cdc686bcd8d0a49e2486e377fbd5c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375554"
---
# <a name="develop-biztalk-applications-using-the-oracle-e-business-suite-adapter"></a>Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発します。
BizTalk アプリケーションを開発する場合で BizTalk プロジェクトを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して、 **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** または**[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** XML スキーマを生成します。 スキーマが生成されると、コンテンツ ベースのルーティング (CBR) を使用するか、または、生成されたスキーマに準拠するメッセージを送受信する BizTalk オーケストレーションを作成することができます。  
  
 CBR は、場所、Oracle E-business Suite に送信されるメッセージには、処理を要する処理は不要のシナリオで使用できます。 たとえば、のみ、特定の種類の受信ポート受信メッセージ、ことがわかっている場合、送信ポートにフィルター式に一致するメッセージをルーティングする送信ポートにフィルターを追加します。  

## <a name="use-orchestration"></a>オーケストレーションを使用します。  
 、BizTalk オーケストレーションの送信を作成およびとの間でメッセージを送受信する受信ポート、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、さらに、メッセージを送信する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 
 
 このセクションでは、BizTalk オーケストレーションを使用して、タスクおよび Oracle E-business Suite を使用して操作を実行する方法の情報を提供します。、[!INCLUDE[adapteroraclebusinessshort_md](../../includes/adapteroraclebusinessshort-md.md)]します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]順番に使用して、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF バインドと対話することができます。  
  
> [!IMPORTANT]
>  使用する、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、常に設定する必要があります、 **EnableBizTalkCompatibilityMode**プロパティをバインド**True**します。 手順については、次を参照してください。 [for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)します。  
  

  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)