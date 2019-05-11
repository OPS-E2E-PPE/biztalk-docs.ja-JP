---
title: BizTalk プロジェクトの作成時の考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, size
- map type name
- projects, naming conventions
- projects, planning
ms.assetid: f6c3dc71-105f-46af-9e6e-9a4c3b982d8c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59b8749928891f963f3ca75032cc133c0ddf7848
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390368"
---
# <a name="considerations-when-creating-biztalk-projects"></a>BizTalk プロジェクトの作成時の考慮事項
このセクションを使用して BizTalk を作成するときに考慮に入れる必要のある情報を提供します。[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
  
## <a name="avoid-compilation-errors-caused-by-projects-that-are-too-large"></a>大きすぎてプロジェクトによって発生したコンパイル エラーを回避します。  
 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コンパイラは正常にコンパイルできませんプロジェクト 75 メガバイトを超えるアセンブリになります。 致命的なエラー CS0013 が生成されるため、コンパイラがサイズの制約に達したときに"予期しないエラーがメタデータをファイルに書き込む\<ファイル名\>"し、停止します。  
  
 この問題を回避するをお勧めのプロジェクトを超えないように 10 メガバイトしない限り、絶対に必要です。 なぜでしょうか。  
  
-   小さいプロジェクトは、少数の展開手順があるため、デプロイする可能性のある簡単です。 小さいプロジェクトで、手順より密接に関連する可能性があります--パートナー割引を取引先や Rfp の処理を管理します。  
  
-   小さいプロジェクトを使用する場合は、バグ、展開の問題、およびその他の問題を分離しやすくなります。 140 のスキーマと多くのカスタム マップ、およびスクリプト プロジェクト内のバグの検索は、10 個のスキーマといくつかのカスタム マップ、およびスクリプト プロジェクトで 1 つの検索よりも困難になります。  
  
-   大規模なプロジェクトを小さなプロジェクトに分割することと、複雑さを軽減できます。 小さいプロジェクトより管理しやすいです。  
  
-   小さいプロジェクトは高速にコンパイルします。  
  
-   厳密に関連するスキーマを持つ小さなプロジェクトに関連付けられていない多数のスキーマを使用した大規模なプロジェクトを分割することと、パフォーマンスが向上する可能性があります。 これは、アセンブリの一部のみが一度に読み込まれるためにです。  
  
## <a name="avoid-using-the-project-name-as-the-map-type-name"></a>マップの型名としてプロジェクト名を使用しないでください。  
 BizTalk プロジェクトに新しいマップを追加するときに[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]型名としてプロジェクト名を使わないでください。 ような 1 つまたは複数のエラーを生成する場合は、"型名\<名前\>' 型に存在しません"。  
  
 BizTalk プロジェクトからマップの種類の名前を変更するには、ソリューション エクスプ ローラー ウィンドウでマップをクリックしてプロパティ ペインで、型名プロパティを確認します。 同じである場合は、変更に依存する構成を変更することを確認する必要があります。  
  
## <a name="visual-studio-team-system-support"></a>Visual Studio Team System のサポート  
 BizTalk プロジェクトで[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]のすべての機能はサポートしない[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]Team System です。 ソース管理機能の[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]Team System が BizTalk Server のサポートされています。 Visual SourceSafe は追跡と BizTalk プロジェクトの成果物のバージョン管理も完全サポートします。