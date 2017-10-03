---
title: "アプリケーションの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b6e325c-a86f-419d-9a27-864f4f035507
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4caf0531ee6cf952bfd343605b9b470c04c636d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-an-application"></a>アプリケーションを作成します。
BizTalk アプリケーションを作成する 3 つの方法はあります。 名前付け、参照、およびアプリケーションにアイテムを展開するためのいくつかのオプションもあります。  
  
## <a name="creating-a-biztalk-application"></a>BizTalk アプリケーションを作成します。  
 3 つの方法は次のとおりです。  
  
1.  BizTalk アプリケーションを作成するには、BizTalk Server 管理コンソールの [新しいアプリケーション] コマンドまたは BTSTask コマンド ライン ツールの AddApp コマンドを使用します。 詳細については、これらのコマンドを使用して、次を参照してください。[アプリケーションを作成する方法](http://go.microsoft.com/fwlink/?LinkId=155007)(http://go.microsoft.com/fwlink/?LinkId=155007)。  
  
2.  他のアプリケーションからエクスポートした .msi ファイルをインポートします。 アプリケーションが現在の BizTalk グループに存在しない場合、アプリケーション (そのアイテムを含む) は現在の BizTalk グループに自動的に作成されます。 アプリケーションのインポートの詳細については、次を参照してください。[を BizTalk アプリケーションをインポートする方法](http://go.microsoft.com/fwlink/?LinkID=154827)(http://go.microsoft.com/fwlink/?LinkID=154827)。  
  
3.  Visual Studio から BizTalk アプリケーションへ BizTalk アセンブリを展開します。 Visual Studio でプロジェクトの展開プロパティで指定されたアプリケーションが現在の BizTalk グループに存在しない場合に自動的に作成されます。 Visual Studio からアセンブリを展開する詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](http://go.microsoft.com/fwlink/?LinkID=154719)(http://go.microsoft.com/fwlink/?LinkID=154719)。  
  
 .Msi ファイルを使用してアプリケーションを展開する送信先アプリケーションする必要はありませんが存在するが、自動的に作成されます。 ただし、別のアプリケーションへのバインドをインポートする送信先アプリケーション存在しなければなりません。 それ以外の場合は、上記の手順のいずれかの操作を実行することによって作成する必要があります。  
  
 特定のアプリケーションを作成するために必要な手順の詳細については、次を参照してください。[アプリケーションを作成する方法](http://go.microsoft.com/fwlink/?LinkId=155007)(http://go.microsoft.com/fwlink/?LinkId=155007)。  
  
## <a name="application-options"></a>アプリケーションのオプション  
 新しいアプリケーションを作成する前に、次の操作を行う必要があります。  
  
-   アプリケーションの BizTalk グループ内で一意の名前を決定します。  
  
-   新しいアプリケーションを新しいアプリケーションで再利用するアイテムを含む任意のアプリケーションからの参照を追加します。 アプリケーション間の依存関係の詳細については、次を参照してください。[の依存関係とアプリケーションの配置](http://go.microsoft.com/fwlink/?LinkId=155008)(http://go.microsoft.com/fwlink/?LinkId=155008)。  
  
-   別のアプリケーションを別のアプリケーションに展開する必要があります、たとえばに共有成果物に一部のアイテムを展開するかどうかを決定します。