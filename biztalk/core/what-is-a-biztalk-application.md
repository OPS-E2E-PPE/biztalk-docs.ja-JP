---
title: "BizTalk アプリケーションについて | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk.System application, about BizTalk.System application
- applications, default
- BizTalk.System application
- artifacts, about artifacts
- applications
- applications, about applications
- applications, warnings
- applications, BizTalk.System
- what's new, applications
- BizTalk.System application, warnings
ms.assetid: 68b5527c-d5e1-453b-a51b-3fc1a1d5dce2
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9ff0e2be82d528c7070955c1ce79b1f5e37cc6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-a-biztalk-application"></a>BizTalk アプリケーションについて
BizTalk アプリケーションは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ビジネス ソリューションの展開、管理、およびトラブルシューティングをすばやく簡単に行えるようにする [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の新機能です。 BizTalk アプリケーションは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ビジネス ソリューションで使用される "アイテム" の論理グループです。 アイテムについては後で詳しく説明します。  
  
 新たに設計された [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] の管理ツールと監視ツールには、この新しい概念が取り入れられ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ビジネス ソリューションを個々のアイテム レベルだけでなくアプリケーション レベルで管理および構成できるようになっています。 アプリケーションを作成してアイテムを追加することで、ソリューション内の複数のアイテムをまとめて 1 つのエンティティとして表示、パッケージ化、展開、および管理できます。 このため、複雑なアプリケーションの数が増えても、容易かつ直観的に個別管理することができます。  
  
 いくつかのツールで説明されるアプリケーションを作成および管理を行うこともできます[アプリケーションの展開と管理ツール](../core/application-deployment-and-management-tools.md)です。  
  
 次の図に、2 つの BizTalk アプリケーションと、各アプリケーションに含まれるアイテムを示します。  
  
 ![BizTalk アプリケーションとアイテム](../core/media/biztalkapplication.gif "BizTalkApplication")  
  
## <a name="artifacts"></a>成果物  
 アイテムには、次のものがあります。  
  
-   BizTalk アセンブリ、およびアセンブリに含まれる BizTalk 固有のリソース (オーケストレーション、パイプライン、スキーマ、およびマップ)  
  
-   BizTalk 固有のリソースを含まない .NET アセンブリ  
  
-   ポリシー  
  
-   送信ポート、送信ポート グループ、受信場所、および受信ポート  
  
-   ソリューションで使用されるその他のアイテム (証明書、COM コンポーネント、スクリプトなど)  
  
 各アイテムの種類に関する背景情報については、次を参照してください。[ランタイム アーキテクチャ](../core/runtime-architecture.md)です。 追加の詳細については、削除、および構成の成果物を参照してください[成果物の管理](../core/managing-artifacts.md)です。  
  
 アプリケーションには、ビジネス ソリューションで使用されているすべてのアイテムを含めることも、一部のみを含めることもできます。 アイテムを 1 つのアプリケーションに配置した方がよいか、2 つ以上のアプリケーションに分けた方がよいかは、アイテムの展開方法によって異なります。 成果物をグループ化する方法を決定する方法の詳細については、次を参照してください。 [BizTalk アプリケーションを配置するためのベスト プラクティス](../core/best-practices-for-deploying-a-biztalk-application.md)です。  
  
## <a name="the-default-application"></a>既定のアプリケーション  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] をインストールして構成すると、"BizTalk アプリケーション 1" という名前の既定のアプリケーションが作成されます。 異なるアプリケーションにアイテムをグループ化のベスト プラクティスについては、次を参照してください。 [BizTalk アプリケーションを配置するためのベスト プラクティス](../core/best-practices-for-deploying-a-biztalk-application.md)です。 既定のアプリケーションを変更したり、既定のアプリケーションの名前を変更したりすることもできます。  
  
 次のシナリオでは、アイテムは自動的に既定のアプリケーションに追加されます。  
  
-   アプリケーション名を指定せずに、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] から [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にアセンブリを展開する場合。 詳細については、次を参照してください。[を Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)です。  
  
-   BTSTask を使用して、アプリケーション名を指定せずにアイテムをアプリケーションに追加する場合。 詳細については、次を参照してください。 [AddResource コマンド](../core/addresource-command.md)です。  
  
-   BTSTask を使用して、アプリケーション名を指定せずにアプリケーションの .msi ファイルをインポートする場合。 詳細については、次を参照してください。 [ImportApp コマンド](../core/importapp-command.md)です。  
  
## <a name="the-biztalksystem-application"></a>BizTalk.System アプリケーション  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] をインストールして構成すると、BizTalk.System という名前のアプリケーションが自動的に作成され、既定のスキーマやパイプラインなど、すべての BizTalk アプリケーションで使用される一般的なアイテムが格納されます。 BizTalk.System とそのアイテムは読み取り専用です。 BizTalk.System を削除したり、名前を変更したりすることはできません。また、BizTalk.System に含まれるアイテムを削除したり、名前を変更したり、移動したりすることもできません。  
  
> [!IMPORTANT]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のすべてのアプリケーションには、自動的に BizTalk.System アプリケーションへの参照が含まれています。 これは、BizTalk.System 内のアイテムがすべての BizTalk アプリケーションで使用されるためです。 BizTalk.System アプリケーションへの参照は削除しないでください。 削除すると、アプリケーションが正しく機能しなくなる可能性があります。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの展開と管理を理解します。](../core/understanding-biztalk-application-deployment-and-management.md)