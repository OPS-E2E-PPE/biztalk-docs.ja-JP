---
title: BizTalk server アセンブリを展開する方法 |Microsoft Docs
description: アセンブリを GAC に展開し、BizTalk server アセンブリのバージョン管理を有効にします。
ms.custom: ''
ms.date: 01/21/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7f99ed5-b64a-4a38-99d7-83070fb69030
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b875a1fd724e9807362b23a5fa884cec3077f53d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358123"
---
# <a name="biztalk-assemblies"></a>BizTalk アセンブリ
Microsoft BizTalk Server と .NET Framework の最も重要な側面はすべての BizTalk Server アイテムです。マップやスキーマ、オーケストレーション、パイプライン、.NET アセンブリにコンパイルします。 この設計の 2 つの最も重要な意味は、これらのアセンブリが厳密な名前は、必要し、そのため、それらも .NET のバージョン管理の規則に従うことです。 これの主な影響は、別の .NET プロジェクトまたはアセンブリ (BizTalk プロジェクトを含む) の特定のバージョンに対して構築されると、BizTalk プロジェクトは、そのバージョンを使用して、新しいバージョンに対して再構築されるまでは引き続きです。  
  
## <a name="net-versioning-and-assemblies"></a>.NET のバージョン管理とアセンブリ  
 一般的な問題は、BizTalk プロジェクトのバージョン番号が変更されていないと、アセンブリを停止してに、型が読み込まれている BizTalk ホスト インスタンスを開始することがなく再展開は、.NET のバージョン管理に関連する開発中に発生します。  
  
 プロセスを再度実行すると、ときに、変更は有効になりません。 これは .NET アセンブリがメモリに読み込まれる方法です。 ホストでは、アセンブリのメモリ内コピーを既に持っているために、新しいコピーがグローバル アセンブリ キャッシュに切り替わるときに、アセンブリは読み込むは。 たとえば、オーケストレーションでのアセンブリのバージョン 1.0.0.0 を配置して実行、および変更は、オーケストレーションに加え、バージョン番号は変更されません、し変更は有効になりません。 アセンブリのインメモリ コピーがリリースされた後、ホスト インスタンスを停止すると、およびホスト インスタンスの開始時にもう一度アセンブリの新しいコピーを再読み込みして変更を取得します。 新しいバージョンがデプロイされている場合は、バージョン 2.0.0.0 以降、およびそれが読み込まれた後、変更が有効になっているとします。  
  
 2 つのプロセスは、アセンブリを BizTalk Server に展開します。 最初の部分では、アセンブリを使用する各サーバーでグローバル アセンブリ キャッシュ (GAC) に厳密な名前のアセンブリが展開された従来の .NET アセンブリの配置です。 2 番目の手順では、BizTalk Server 管理データベースにアセンブリとその型に関するメタデータを展開します。 BizTalk Server での BizTalk Server アセンブリが読み込まれると、管理データベースにある、厳密な名前を使用して最も多くの場合、ロードされます。  
  
## <a name="deploying-biztalk-server-assemblies-to-the-gac"></a>BizTalk Server アセンブリを GAC に展開します。  
 組み込み型の BizTalk Server から派生したクラスにコンパイルされる、開発者が作成される BizTalk Server アイテム。 たとえば、オーケストレーションは、Microsoft.BizTalkXLANGs.BTXEngine.BTXService から派生したクラスになります。 これらの基本クラスは、グローバル アセンブリ キャッシュにアセンブリに配置され、これらのアセンブリが GAC の他のアセンブリに依存しているため、開発者のアセンブリが GAC に展開を取得する必要がありますもします。  
  
 グローバル アセンブリ キャッシュに展開されている BizTalk Server アイテムのもう 1 つの重要な意味であり、したがってされる厳密な名前付き、厳密な名前付きアセンブリも厳密な名前のない他のアセンブリを呼び出すことはできません。 これは、これらの BizTalk Server アセンブリによって使用されているアセンブリ、開発者が作成する必要がありますもする厳密なという名前のことを意味します。 同様に、アセンブリを GAC に展開されている特定のパスを使用せず、他のアセンブリを読み込むことは、GAC からアセンブリを読み込む必要があります。  
  
 パイプライン コンポーネントの開発者のツールボックスに追加された[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]パイプライン デザイナーにドラッグすることに利用できるようにします。 BizTalk Server パイプラインが .NET アセンブリにコンパイルされると、さまざまな段階で、パイプラインのすべてのコンポーネントについては、アセンブリにコンパイルされます。 このパイプラインが BizTalk Server に展開されると、ファイル名などのコンポーネントに関する情報が BizTalk 管理データベースに挿入し、パイプライン アセンブリが GAC に展開します。 BizTalk パイプライン コンポーネントが依存する追加のアセンブリは、実行時に検出するために GAC にも展開する必要があります。 パイプライン コンポーネント アセンブリは、実行時に BizTalk パイプラインによってアクセスできるように BizTalk Server\Pipeline コンポーネント ディレクトリにもコピーする必要があります。 パイプラインが実行されるときに、これらのコンポーネントが読み込まれ、実装するインターフェイスが必要に応じて呼び出されます。  
  
## <a name="see-also"></a>参照  
 [ランタイム アーキテクチャ](../core/runtime-architecture.md)