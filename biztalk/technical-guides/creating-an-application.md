---
title: アプリケーションを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b6e325c-a86f-419d-9a27-864f4f035507
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 772ba15d357715d5ceeca3c229167a96f7ef6c60
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987547"
---
# <a name="creating-an-application"></a>アプリケーションを作成します。
BizTalk アプリケーションを作成する 3 つの方法はあります。 名前付け、参照、およびアプリケーションにアイテムを展開するいくつかのオプションもあります。  
  
## <a name="creating-a-biztalk-application"></a>BizTalk アプリケーションを作成します。  
 3 つの方法は次のとおりです。  
  
1. BizTalk アプリケーションを作成するには、BizTalk Server 管理コンソールの [新しいアプリケーション] コマンドまたは BTSTask コマンド ライン ツールの AddApp コマンドを使用します。 詳細については、これらのコマンドを使用して、[アプリケーションを作成する方法](http://go.microsoft.com/fwlink/?LinkId=155007)(http://go.microsoft.com/fwlink/?LinkId=155007)を参照してください。  
  
2. 他のアプリケーションからエクスポートした .msi ファイルをインポートします。 アプリケーションが現在の BizTalk グループに存在しない場合、アプリケーション (そのアイテムを含む) は現在の BizTalk グループに自動的に作成されます。 アプリケーションのインポートに関する詳細については、[BizTalk アプリケーションをインポートする方法](http://go.microsoft.com/fwlink/?LinkID=154827)(http://go.microsoft.com/fwlink/?LinkID=154827)を参照してください。  
  
3. Visual Studio から BizTalk アプリケーションへ BizTalk アセンブリを展開します。 Visual Studio でプロジェクトの配置プロパティで指定されたアプリケーションが現在の BizTalk グループに存在しない場合に自動的に作成されます。 Visual Studio からアセンブリを展開の詳細については、[BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](http://go.microsoft.com/fwlink/?LinkID=154719)(http://go.microsoft.com/fwlink/?LinkID=154719)を参照してください。  
  
   .Msi ファイルを使用してアプリケーションを展開するには、コピー先のアプリケーションは存在しますが必要ありませんが、自動的に作成されます。 ただし、別のアプリケーションへのバインドをインポートするコピー先のアプリケーションが既に存在します。 それ以外の場合は、上記の手順のいずれかを実行して作成する必要があります。  
  
   特定のアプリケーションを作成するために必要な手順の詳細については、[アプリケーションを作成する方法](http://go.microsoft.com/fwlink/?LinkId=155007)(http://go.microsoft.com/fwlink/?LinkId=155007)を参照してください。  
  
## <a name="application-options"></a>アプリケーションのオプション  
 新しいアプリケーションを作成する前に、次の操作を行う必要があります。  
  
-   アプリケーションの BizTalk グループ内で一意の名前を決定します。  
  
-   新しいアプリケーションで再利用するアイテムを含む任意のアプリケーションに新しいアプリケーションからの参照を追加します。 アプリケーション間の依存関係の詳細については、[依存関係とアプリケーションの展開](http://go.microsoft.com/fwlink/?LinkId=155008)(http://go.microsoft.com/fwlink/?LinkId=155008)を参照してください。  
  
-   別のアプリケーションに配置するか、共有アイテムなどの別のアプリケーションにいくつかの成果物を配置するかどうかを決定します。