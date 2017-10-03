---
title: "BizTalk プロジェクトを作成する際の考慮事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects, size
- map type name
- projects, naming conventions
- projects, planning
ms.assetid: f6c3dc71-105f-46af-9e6e-9a4c3b982d8c
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e9d05e07465d834f587f79d50f04bec18a89506
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-when-creating-biztalk-projects"></a>BizTalk プロジェクトを作成する際の考慮事項
ここでは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して BizTalk プロジェクトを作成する際に考慮すべき情報について説明します。  
  
## <a name="avoid-compilation-errors-caused-by-projects-that-are-too-large"></a>サイズの大きなプロジェクトが原因となるコンパイル エラーの回避  
 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コンパイラは、75 MB を超えるアセンブリのプロジェクトを正しくコンパイルできません。 致命的なエラー CS0013 が生成されるため、コンパイラがサイズ制限に達すると"予期しないエラーがメタデータをファイルに書き込み\<ファイル名 >"され、停止します。  
  
 この問題を回避するには、どうしても必要な場合を除き、プロジェクトが 10 MB を超えないようにすることをお勧めします。 なぜでしょうか。  
  
-   小さいプロジェクトは、展開手順が少ないので、展開が簡単になります。 また、小さいプロジェクトを使用すると、相互の関連性が高い手順 (取引先の割引や見積依頼書の処理など) が多くなります。  
  
-   小さいプロジェクトでは、バグ、展開の問題、および他の問題を見分けることが簡単になります。 スキーマの数が 140 あり、使用するカスタム マップやカスタム スクリプトの数が多いプロジェクトのバグを発見することは、スキーマの数が 10 で、使用するカスタム マップやカスタム スクリプトの数が少ないプロジェクトのバグを発見するよりも困難です。  
  
-   大きなプロジェクトを小さなプロジェクトに分割すると、複雑さを軽減できます。 小さいプロジェクトの方が管理が簡単です。  
  
-   小さいプロジェクトは、高速にコンパイルされます。  
  
-   関連性のない多くのスキーマを持つ大きなプロジェクトを、関連性の高いスキーマを持つ小さなプロジェクトに分割すると、パフォーマンスが向上します。 これは、ため、一度に読み込まれるアセンブリの一部のみです。  
  
## <a name="avoid-using-the-project-name-as-the-map-type-name"></a>マップの型名としてプロジェクト名を使用することの回避  
 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で新しいマップを BizTalk プロジェクトに追加する際に、マップの型名としてプロジェクト名を使用しないでください。 コンパイラはのような 1 つまたは複数のエラーを生成する場合、"型名\<名 >' 型に存在しません"です。  
  
 BizTalk プロジェクトからマップの型名を変更するには、[ソリューション エクスプローラー] ペインのマップをクリックし、[プロパティ] ペインの "型名" プロパティを確認してください。 マップの型名が同じ場合、型名を修正して、型名に依存する構成を変更してください。  
  
## <a name="visual-studio-team-system-support"></a>Visual Studio Team System のサポート  
 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の BizTalk プロジェクトでは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System のすべての機能が直接サポートされるわけではありません。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System のソース管理機能は、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] でサポートされます。 また、Visual SourceSafe も、BizTalk プロジェクト アイテムの追跡とバージョン管理で完全にサポートされます。