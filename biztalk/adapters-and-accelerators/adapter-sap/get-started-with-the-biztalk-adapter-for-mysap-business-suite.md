---
title: BizTalk Adapter 用 mySAP Business Suite の概要 |Microsoft ドキュメント
description: カスタム Rfc のインストール、アダプターについて、SAP、mySAP アダプターの BizTalk アダプター パック (BAP) を使用するチュートリアルのステップでタスクを RFC および IDOC 完了
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
ms.openlocfilehash: 3e5607a255f50bf5295d4ea22c9a680d86f38e5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216322"
---
# <a name="get-started-with-the-biztalk-adapter-for-mysap-business-suite"></a>BizTalk Adapter 用 mySAP Business Suite の概要します。
このセクションでは Microsoft に新しいユーザーのアダプター、前提条件、およびトピックの概要を説明する[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 機能についても説明[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]とアダプターを使用して SAP システムで実行できるさまざまな操作です。  

## <a name="what-is-an-adapter"></a>アダプターとは何ですか。 
アダプターは、ソフトウェア コンポーネントと基幹業務 (LOB) システムからメッセージを送受信することができます。 アダプターの主な設計目標は、取引先間でのビジネス ドキュメントの交換を容易にです。 各ビジネス システムは、特定のドキュメント形式およびプロトコルに従うことがあります、ために、アダプターは、共通に認識される標準と、ユーザーに一貫したインターフェイスを提供するプロトコルに準拠した配信メカニズムを使用する必要があります。  
  
 アダプターは、2 つのカテゴリに分類できます。  
  
-   **LOB アダプタ**です。 このようなアダプターが LOB システムへのアクセスをサービス指向のプログラミング モデルを提供、SAP の Siebel アダプターなどです。  
  
-   **データ アダプター**です。 このようなアダプターがデータベースにアクセスできるサービス指向のプログラミング モデルを提供、Oracle データベースまたは SQL Server 用のアダプターなどです。  
  
 5 つのアダプタでは、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:  
  
-   [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)](、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])  
  
-   [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)](、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])  
  
-   [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)](、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)](、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]) など、 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])  
  
-   [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)](、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]) など、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])  
  
    > [!NOTE]
    >  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 64 ビット プラットフォームでは使用できません。  
  
 かどうかは既に分かっていなければを使用する方法、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で、社内をお勧めする機能を表示することによって起動してで説明されているアダプターの機能[BizTalk Adapter 用 mySAP Business Suite 理解](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md).  
  
## <a name="next-steps"></a>次の手順  
- [SAP 用データ プロバイダーのカスタム Rfc をインストールします。](install-custom-rfcs-for-the-data-provider-for-sap.md)
  
-   [MySAP Business Suite の BizTalk アダプターを理解します。](understand-biztalk-adapter-for-mysap-business-suite.md)  

- [SAP での RFC および IDOC のタスクを完了](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)
  
-   [SAP アダプタ チュートリアル](sap-adapter-tutorials.md)  