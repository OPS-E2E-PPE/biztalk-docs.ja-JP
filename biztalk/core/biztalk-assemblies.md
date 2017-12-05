---
title: "BizTalk Server 内のアセンブリを展開する方法 |Microsoft ドキュメント"
description: "GAC にアセンブリを展開し、BizTalk Server 内のアセンブリのバージョン管理を有効にします。"
ms.custom: 
ms.date: 01/21/2016
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7f99ed5-b64a-4a38-99d7-83070fb69030
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb6c787219855ca219808fc1e95c0caefbf12a9d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="biztalk-assemblies"></a>BizTalk アセンブリ
Microsoft BizTalk Server と .NET Framework の特徴として最も重要な点は、BizTalk Server のアイテム、マップ、スキーマ、オーケストレーション、パイプラインがすべて、.NET アセンブリにコンパイルされることです。 このしくみが意味するのは、これらのアセンブリに厳密な名前が必要であり、そのために .NET のバージョン管理規則にも従う必要が生じることです。 結果として、BizTalk のプロジェクトは、別の .NET プロジェクトまたはアセンブリ (BizTalk プロジェクトを含む) の特定のバージョンに対して構築されると、新しいバージョンに対して再構築されるまではそのバージョンを使い続けることになります。  
  
## <a name="net-versioning-and-assemblies"></a>.NET のバージョン管理とアセンブリ  
 .NET のバージョン管理に関連する開発中の問題は、BizTalk プロジェクトのバージョン番号を変更せず、型の読み込み先である BizTalk ホストのインスタンスを停止してから開始せずにアセンブリを再展開した場合によく発生します。  
  
 プロセスを再実行した場合、変更は適用されません。 これは、メモリへの .NET アセンブリの読み込み方法が原因です。 ホストのメモリ内には既にアセンブリのコピーがあるため、新しいコピーをグローバル アセンブリ キャッシュに入れても、アセンブリの再読み込みは行われません。 たとえば、オーケストレーションのあるアセンブリのバージョン 1.0.0.0 を再展開して実行した場合、オーケストレーションに変更を加えても、バージョン番号を変更しなければ、変更は反映されません。 ホストのインスタンスを停止した後、メモリ内のアセンブリのコピーが解放され、ホストインスタンスが再開すると、アセンブリの新しいコピーを再度読み込んで変更を取り込みます。 新しいバージョン (たとえば、バージョン 2.0.0.0) が展開されて読み込まれると、変更が反映されます。  
  
 アセンブリは 2 段階のプロセスで BizTalk Server に展開されます。 第 1 段階は、従来の .NET アセンブリの展開で、アセンブリを使用する各サーバーの Global Assembly Cache (GAC) に、厳密な名前のアセンブリが展開されます。 第 2 段階では、アセンブリに関するメタデータとその型が BizTalk Server 管理データベースに展開されます。 BizTalk Server アセンブリが BizTalk Server に読み込まれるとき、通常は管理データベースに保管されている厳密な名前を使用して読み込まれます。  
  
## <a name="deploying-biztalk-server-assemblies-to-the-gac"></a>GAC への BizTalk Server アセンブリの展開  
 開発者が作成する BizTalk Server のアイテムは、BizTalk Server に組み込まれている型から派生したクラスとしてコンパイルされます。 たとえば、オーケストレーションは、Microsoft.BizTalkXLANGs.BTXEngine.BTXService から派生したクラスになります。 その理由は、これらの基本クラスはアセンブリでグローバル アセンブリ キャッシュに展開されますが、これらのアセンブリは GAC の他のアセンブリと依存関係があるため、開発者のアセンブリも GAC に展開される必要があるからです。  
  
 BizTalk Server アイテムをグローバル アセンブリ キャッシュに展開し、そのために厳密な名前を付けるということは、厳密な名前の付いているアセンブリから厳密な名前の付いていない他のアセンブリは呼び出せないということも意味しています。 つまり、開発者が作成したアセンブリのうち、これらの BizTalk Server アセンブリで使用されるものにはすべて厳密な名前を付ける必要があります。 同様に、GAC に展開されたアセンブリは、特定のパスを使用しないで他のアセンブリを読み込みますが、それらのアセンブリを GAC から読み込む必要があります。  
  
 パイプライン コンポーネントは [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の開発者のツールボックスに追加され、パイプライン デザイナーにドラッグできるようになります。 BizTalk Server パイプラインを .NET アセンブリにコンパイルすると、パイプラインのさまざまなステージの全コンポーネントに関する情報がアセンブリにコンパイルされます。 このパイプラインが BizTalk Server に展開されると、ファイル名など、コンポーネントに関する情報が BizTalk 管理データベースに挿入し、パイプライン アセンブリは GAC に展開します。 実行時に検出するために、BizTalk パイプライン コンポーネントが依存する追加のアセンブリを GAC に展開も必要があります。 パイプライン コンポーネント アセンブリは、実行時に BizTalk パイプラインによってにアクセスできるように BizTalk Server\Pipeline コンポーネント ディレクトリにもコピーする必要があります。 パイプラインが実行されると、これらのコンポーネントが読み込まれ、コンポーネントが実装するインターフェイスが必要に応じて呼び出されます。  
  
## <a name="see-also"></a>参照  
 [ランタイム アーキテクチャ](../core/runtime-architecture.md)