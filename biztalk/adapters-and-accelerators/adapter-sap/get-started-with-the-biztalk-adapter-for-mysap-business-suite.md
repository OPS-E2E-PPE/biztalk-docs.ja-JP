---
title: BizTalk Adapter for mySAP Business Suite の概要 |Microsoft Docs
description: カスタム Rfc をインストール、アダプターについて、SAP、BizTalk アダプター パック (BAP) での mySAP アダプターを使用するチュートリアルの手順で RFC および IDOC のタスクを完了
ms.custom: ''
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2013253-f911-4e35-a33a-b4a9bcb136aa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02112b6974a537c9f66cc301014ae16bb4bf326f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967473"
---
# <a name="get-started-with-the-biztalk-adapter-for-mysap-business-suite"></a>BizTalk Adapter for mySAP Business Suite の概要します。
このセクションでは、ユーザーが Microsoft に新しいアダプター、前提条件、およびトピックの概要を示します[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 機能について説明します[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]とアダプターを使用して SAP システムで実行できるさまざまな操作です。  

## <a name="what-is-an-adapter"></a>アダプターとは何ですか。 
アダプターは、基幹業務 (LOB) システムとのメッセージを送受信することができるソフトウェア コンポーネントです。 アダプターの主な設計目標は、取引先間でのビジネス ドキュメントの交換を促進します。 各ビジネス システムは、特定のドキュメント形式とプロトコルに従うことがあります、ため、アダプターは、一般的な規格と、ユーザーに統一インターフェイスを提供するプロトコルに準拠した配信メカニズムを使用する必要があります。  
  
 アダプターは、2 つのカテゴリに分類できます。  
  
- **LOB アダプタ**します。 このようなアダプターへのアクセスの LOB システムへのサービス指向のプログラミング モデルを提供する、SAP や Siebel アダプターなど。  
  
- **データ アダプター**します。 このようなアダプターは、access データベースにサービス指向のプログラミング モデルを提供 — たとえば、Oracle database または SQL Server のアダプター。  
  
  5 つのアダプタでは、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:  
  
- [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] (、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])  
  
- [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] (、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])  
  
- [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] (、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])  
  
- [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] (、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]) など、 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])  
  
- [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] (、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]) など、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])  
  
  > [!NOTE]
  >  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 64 ビット プラットフォームでは使用できません。  
  
  かどうかは既にわからないを使用する方法、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で、社内をお勧めして機能の探索を開始してで説明されているアダプターの機能を[理解の BizTalk Adapter 用 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md).  
  
## <a name="next-steps"></a>次のステップ  
- [Data Provider for SAP のカスタム RFC をインストールする](install-custom-rfcs-for-the-data-provider-for-sap.md)
  
-   [BizTalk Adapter for mySAP Business Suite について](understand-biztalk-adapter-for-mysap-business-suite.md)  

- [SAP で RFC および IDOC のタスクを実行する](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)
  
-   [SAP アダプター チュートリアル](sap-adapter-tutorials.md)  