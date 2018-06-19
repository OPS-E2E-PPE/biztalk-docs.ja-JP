---
title: BizTalk プロジェクトに含まれる BizTalk Namespace 参照について |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- System.Xml namespace
- Microsoft.BizTalk.GlobalPropertySchemas namespace
- namespaces, System.Xml namespace
- System namespace
- namespaces, System namespace
- namespaces, Microsoft.BizTalk.GlobalPropertySchemas namespace
- Microsoft.BizTalk.DefaultPipelines namespace
- projects, namespaces
- namespaces, warnings
- namespaces, Microsoft.BIzTalk.DefaultPipelines namespace
- namespaces
ms.assetid: cb642eac-7307-44f8-bbba-3ae364e11ea2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 820e15eb3524713dfd7d3f86311ca262fde191d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225178"
---
# <a name="about-biztalk-namespace-references-included-in-biztalk-projects"></a>BizTalk プロジェクト内の BizTalk 名前空間参照について
新しい BizTalk プロジェクトを追加すると、既定で次の名前空間が設定されます。  
  
-   **Microsoft.BizTalk.DefaultPipelines**  
  
-   **Microsoft.BizTalk.GlobalPropertySchemas**  
  
-   **システム**  
  
-   **System.Xml**  
  
 また、新しい参照および Web 参照をプロジェクトに追加することもできます。 使用して追加する方法についての参照を**プロジェクト**] メニューの [を参照してください[Visual Studio を使って](../core/using-visual-studio.md)です。 Web 参照を追加する方法については、次を参照してください。 [Web 参照を追加する](../core/adding-web-references.md)です。  
  
> [!CAUTION]
>  既定の参照は削除しないでください。 既定の参照を削除すると、プロジェクト内の BizTalk アイテムを参照するときに問題が発生する場合があります。 ソリューション エクスプローラーで既定の参照を復元できます。  
  
> [!CAUTION]
>  BizTalk プロジェクトが別のアセンブリを参照したときに、そのアセンブリが更新されている場合、その更新または変更は BizTalk プロジェクトに自動的には反映されません。 ソリューション エクスプローラーで期限切れの参照を削除してから、参照を追加する必要があります (アセンブリの再参照)。 または、ソリューションを閉じて再度開きます。 いずれの場合も、参照されるアセンブリの最新の更新がプロジェクトで利用可能になります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Microsoft.BizTalk.DefaultPipelines の参照](../core/microsoft-biztalk-defaultpipelines-reference.md)  
  
-   [Microsoft.BizTalk.GlobalPropertySchemas 参照](../core/microsoft-biztalk-globalpropertyschemas-reference.md)  
  
-   [システムのリファレンス](../core/system-reference.md)  
  
-   [System.Xml 参照](../core/system-xml-reference.md)