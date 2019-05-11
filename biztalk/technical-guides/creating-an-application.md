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
ms.openlocfilehash: 7e93e3feacf3e8243fc6871fe3f18c17aa9ccba0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305984"
---
# <a name="creating-an-application"></a>アプリケーションの作成
BizTalk アプリケーションを作成する 3 つの方法はあります。 名前付け、参照、およびアプリケーションにアイテムを展開するいくつかのオプションもあります。  
  
## <a name="creating-a-biztalk-application"></a>BizTalk アプリケーションを作成します。  
 3 つの方法は次のとおりです。  
  
1. BizTalk アプリケーションを作成するには、BizTalk Server 管理コンソールの [新しいアプリケーション] コマンドまたは BTSTask コマンド ライン ツールの AddApp コマンドを使用します。 詳細については、これらのコマンドを使用して、次を参照してください。[アプリケーションを作成する方法](http://go.microsoft.com/fwlink/?LinkId=155007)(http://go.microsoft.com/fwlink/?LinkId=155007)します。  
  
2. 他のアプリケーションからエクスポートした .msi ファイルをインポートします。 アプリケーションが現在の BizTalk グループに存在しない場合、アプリケーション (そのアイテムを含む) は現在の BizTalk グループに自動的に作成されます。 アプリケーションのインポートに関する詳細については、次を参照してください。 [BizTalk アプリケーションをインポートする方法](http://go.microsoft.com/fwlink/?LinkID=154827)(http://go.microsoft.com/fwlink/?LinkID=154827)します。  
  
3. Visual Studio から BizTalk アプリケーションへ BizTalk アセンブリを展開します。 Visual Studio でプロジェクトの配置プロパティで指定されたアプリケーションが現在の BizTalk グループに存在しない場合に自動的に作成されます。 Visual Studio からアセンブリを展開の詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](http://go.microsoft.com/fwlink/?LinkID=154719)(http://go.microsoft.com/fwlink/?LinkID=154719)します。  
  
   .Msi ファイルを使用してアプリケーションを展開するには、コピー先のアプリケーションは存在しますが必要ありませんが、自動的に作成されます。 ただし、別のアプリケーションへのバインドをインポートするコピー先のアプリケーションが既に存在します。 それ以外の場合は、上記の手順のいずれかを実行して作成する必要があります。  
  
   特定のアプリケーションを作成するために必要な手順の詳細については、次を参照してください。[アプリケーションを作成する方法](http://go.microsoft.com/fwlink/?LinkId=155007)(http://go.microsoft.com/fwlink/?LinkId=155007)します。  
  
## <a name="application-options"></a>アプリケーションのオプション  
 新しいアプリケーションを作成する前に、次の操作を行う必要があります。  
  
-   アプリケーションの BizTalk グループ内で一意の名前を決定します。  
  
-   新しいアプリケーションで再利用するアイテムを含む任意のアプリケーションに新しいアプリケーションからの参照を追加します。 アプリケーション間の依存関係の詳細については、次を参照してください。[依存関係とアプリケーションの展開](http://go.microsoft.com/fwlink/?LinkId=155008)(http://go.microsoft.com/fwlink/?LinkId=155008)します。  
  
-   別のアプリケーションに配置するか、共有アイテムなどの別のアプリケーションにいくつかの成果物を配置するかどうかを決定します。