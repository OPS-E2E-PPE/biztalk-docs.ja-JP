---
title: "BizTalk プロジェクト システムについて |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects, about projects
- applications, creating
- creating, applications
- creating, business solutions
- business solutions, creating
ms.assetid: 69807e57-356e-451d-b803-4253b891b617
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddff6ff13611ee404a5517384455b0c59f968ee0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="about-the-biztalk-project-system"></a>BizTalk プロジェクト システムについて
BizTalk プロジェクト システムを使用して、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションやビジネス ソリューションの一部またはすべてを作成できます。 ソリューションの中核となる要素は、スキーマ、オーケストレーション、Web メッセージの種類、クラス、パイプライン、マップ、参照などの項目の集合である BizTalk プロジェクトです。ユーザーは、これらの項目をビルドしてアセンブリを生成し、生成したアセンブリを展開します。  
  
 比較的単純なビジネス ソリューションは、1 つのアセンブリに生成された 1 つの BizTalk プロジェクトのみで構成される場合があります。 複雑なビジネス ソリューション (さまざまなシステムとプロセスを統合するソリューションなど) の場合、BizTalk ソリューションでは、さまざまな BizTalk プロジェクトから多数のアセンブリが生成され、それらのアセンブリは複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターに展開されることが考えられます。  
  
> [!IMPORTANT]
>  アセンブリ名にはコンマを使用できません。  
  
 BizTalk プロジェクトを作成すると、次に示すファイルの種類が 1 つ以上含まれます。 これらのファイルは、ソリューションの作成時にそれぞれ独自の役割を果たします。BizTalk プロジェクト システムでは、ファイルの種類ごとに対応するグラフィカルなデザイン ツールが用意されています。  
  
-   **オーケストレーションです。** : オーケストレーションとは、ビジネス プロセスのワークフローを表すものです。 オーケストレーション デザイナーを使用して、オーケストレーションをデザインします。 オーケストレーション デザイナーの詳細については、次を参照してください。[オーケストレーション デザイナーを使用してオーケストレーションを作成する](../core/creating-orchestrations-using-orchestration-designer.md)です。  
  
-   **スキーマです。** : スキーマは、XML ドキュメントの構造を記述します。 スキーマによって、組織内のアプリケーション間で、または取引先の間で情報を交換します。 BizTalk エディターは、スキーマを定義するプロセスを単純化します。 BizTalk エディターの詳細については、次を参照してください。 [BizTalk エディターを使用してスキーマを作成する](../core/creating-schemas-using-biztalk-editor.md)です。  
  
-   **マップします。** : マップはデータをある形式から別の形式に変換します。 BizTalk マッパーは、送信元スキーマと送信先スキーマを並べて表示し、さまざまなメッセージのデータ要素間の変換を定義できるようにします。 BizTalk マッパーの詳細については、次を参照してください。 [BizTalk マッパーを使用してマップを作成する](../core/creating-maps-using-biztalk-mapper.md)です。  
  
-   **パイプラインです。** : パイプラインは、さまざまな操作を実行し、後続の処理のために受信メッセージまたは送信メッセージを準備します。 パイプライン デザイナーでは、暗号化と復号化、圧縮、再フォーマッティング、検証などの操作を実装できます。 パイプライン デザイナーの詳細については、次を参照してください。[パイプライン デザイナーを使用してパイプラインを作成する](../core/creating-pipelines-using-pipeline-designer.md)です。  
  
 BizTalk プロジェクトは Team Foundation Server (TFS) と互換性があります。 設計の詳細については、開発、および tfs では、BizTalk Server 内でソリューションの配置について[統合ソリューションの開発 BizTalk Server と Team Foundation Server を使用して](http://www.microsoft.com/downloads/details.aspx?FamilyID=ed7bd0ee-1385-4041-8f2a-354594ee88f3&DisplayLang=en)です。  
  
> [!IMPORTANT]
>  TFS ビルドは “MSBuild Platform” というプロパティを公開し、このプロパティは 3 つの値 (“Auto”、“x86”、“x64”) をとることができます。 ビルドを成功させるには、上記のプロパティの値を x86 に設定する必要があります。  
  
 BizTalk プロジェクトは、Visual Studio の他のプロジェクトと共存できます。 Visual Studio のすべてのプロジェクト システムと同様に、BizTalk プロジェクトには、ASP.NET ページなどの他のファイルを含めたり、作成した他のプロジェクトおよびアセンブリを参照できます。 BizTalk プロジェクト テンプレートの詳細については、次を参照してください。 [BizTalk Server プロジェクト テンプレート](../core/biztalk-server-project-templates.md)です。 BizTalk プロジェクトの作成の詳細については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)です。  
  
> [!WARNING]
>  Visual Studio で使用できる他のプロジェクト システムからも BizTalk デザイン ツールにアクセスできますが、ツールの動作は予測できません。 オーケストレーション デザイナー、パイプライン デザイナー、BizTalk エディター、BizTalk マッパーは、BizTalk プロジェクトのコンテキスト内部でのみ使用してください。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション デザイナーを使用してオーケストレーションの作成](../core/creating-orchestrations-using-orchestration-designer.md)   
 [BizTalk エディターを使用してスキーマを作成します。](../core/creating-schemas-using-biztalk-editor.md)   
 [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)   
 [パイプライン デザイナーを使用してパイプラインを作成します。](../core/creating-pipelines-using-pipeline-designer.md)   
 [開発者用ツール](../core/developer-tools.md)