---
title: BizTalk プロジェクトに含まれる BizTalk Namespace 参照について |Microsoft Docs
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
ms.openlocfilehash: 608f3ebf9a80553749fe5de558c2db05e3c7673d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016370"
---
# <a name="about-biztalk-namespace-references-included-in-biztalk-projects"></a>BizTalk プロジェクト内の BizTalk 名前空間参照について
新しい BizTalk プロジェクトを追加すると、既定で次の名前空間が設定されます。  
  
- **Microsoft.BizTalk.DefaultPipelines**  
  
- **Microsoft.BizTalk.GlobalPropertySchemas**  
  
- **システム**  
  
- **System.Xml**  
  
  また、新しい参照および Web 参照をプロジェクトに追加することもできます。 追加の詳細については参照を使用して、**プロジェクト**] メニューの [を参照してください[Visual Studio を使って](../core/using-visual-studio.md)します。 Web 参照を追加する方法の詳細については、次を参照してください。 [Web 参照を追加する](../core/adding-web-references.md)します。  
  
> [!CAUTION]
>  既定の参照は削除しないでください。 既定の参照を削除すると、プロジェクト内の BizTalk アイテムを参照するときに問題が発生する場合があります。 ソリューション エクスプローラーで既定の参照を復元できます。  
  
> [!CAUTION]
>  BizTalk プロジェクトが別のアセンブリを参照したときに、そのアセンブリが更新されている場合、その更新または変更は BizTalk プロジェクトに自動的には反映されません。 ソリューション エクスプローラーで期限切れの参照を削除してから、参照を追加する必要があります (アセンブリの再参照)。 または、ソリューションを閉じて再度開きます。 いずれの場合も、参照されるアセンブリの最新の更新がプロジェクトで利用可能になります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Microsoft.BizTalk.DefaultPipelines の参照](../core/microsoft-biztalk-defaultpipelines-reference.md)  
  
-   [Microsoft.BizTalk.GlobalPropertySchemas 参照](../core/microsoft-biztalk-globalpropertyschemas-reference.md)  
  
-   [System 参照](../core/system-reference.md)  
  
-   [System.Xml 参照](../core/system-xml-reference.md)