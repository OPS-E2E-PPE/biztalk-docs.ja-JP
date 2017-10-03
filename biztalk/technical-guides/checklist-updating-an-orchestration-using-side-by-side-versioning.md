---
title: "チェックリスト: サイド バイ サイドのバージョン管理を使用してオーケストレーションを更新する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97f66987-0269-4dfe-a648-7b68412e86fe
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 110eb0df6373d8679fed0431c91d10a6633e0610
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-updating-an-orchestration-using-side-by-side-versioning"></a>チェックリスト: サイド バイ サイドのバージョン管理を使用してオーケストレーションを更新します。
オーケストレーションへの変更をマップなど、他の成果物の変更よりも複雑にすることができます。 有効期間が短いオーケストレーションがあれば、し、単純な更新プログラムは十分であります。 長時間のオーケストレーションまたは既存のインスタンスを終了することはできませんがある場合、サイド バイ サイドのバージョン管理は唯一の選択肢です。  
  
 オーケストレーションは、実行時間の長いトランザクションを処理するときにすぐに更新されたバージョンのオーケストレーションを変更できません。 元のバージョンが失われないように、そのメッセージを処理を完了するを許可する必要があります。 これを行うには、元のオーケストレーションと同じアプリケーションに、更新されたオーケストレーションを展開します 次に、元のバージョンを停止し、更新されたバージョンを開始して、前のバージョンがインフライト メッセージを引き続き処理する一方で、更新されたバージョンが新しいメッセージをすべて受信するようにします。 元のオーケストレーションですべてのメッセージ処理が完了したら、展開されている BizTalk アプリケーションから元のオーケストレーションを展開解除します。  
  
|手順|リファレンス|  
|-----------|---------------|  
|オーケストレーションに必要な変更を行った後は、アセンブリのバージョン番号をインクリメントします。|[アセンブリを更新する方法](../technical-guides/how-to-update-an-assembly.md)|  
|Visual Studio から BizTalk アプリケーションにアセンブリを展開し、アセンブリをテストします。 **注:**アセンブリを GAC にインストールする展開オプションを選択するかどうかを確認します。|[BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](http://go.microsoft.com/fwlink/?LinkID=154719)(http://go.microsoft.com/fwlink/?LinkID=154719)。|  
|.Msi ファイルに、テスト環境にアプリケーションからアセンブリをエクスポートします。|[アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)|  
|.Msi ファイルを更新するオーケストレーションを含む、運用環境で BizTalk アプリケーションにインポートします。 **注:**次の手順を使用するには、実稼働環境に展開すると、アセンブリをテストします。|[アプリケーションを .msi ファイルからインポートする方法](../technical-guides/how-to-import-an-application-from-an-msi-file.md)|  
|元のオーケストレーションとして同じバインディングを使用して、更新されたオーケストレーションをバインドします。|[オーケストレーションのバインドを構成する方法](http://go.microsoft.com/fwlink/?LinkId=154850)(http://go.microsoft.com/fwlink/?LinkId=154850)。|  
|元のオーケストレーションを参加解除して、更新されたオーケストレーションを開始します。 **注:**メッセージの消失を回避するのにはこのプログラムで実行します。|プログラムによって、オーケストレーションの展開に関する詳細については、次を参照してください。[展開とプログラム、オーケストレーションの新しいバージョンを開始](http://go.microsoft.com/fwlink/?LinkId=154851)(http://go.microsoft.com/fwlink/?LinkId=154851)。<br /><br /> オーケストレーションを手動で展開の詳細についてでは、次を参照してください。[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ヘルプ。<br /><br /> -   [オーケストレーションを参加解除する方法](http://go.microsoft.com/fwlink/?LinkId=154852)(http://go.microsoft.com/fwlink/?LinkId=154852)。<br />-   [オーケストレーションを参加させる方法](http://go.microsoft.com/fwlink/?LinkId=154853)(http://go.microsoft.com/fwlink/?LinkId=154853)。<br />-   [オーケストレーションを開始する方法](http://go.microsoft.com/fwlink/?LinkId=154854)(http://go.microsoft.com/fwlink/?LinkId=154854)。|  
|システム監視グループ ハブを使用して元のオーケストレーションのバージョンのインスタンスがクエリ ビュー ページします。|[オーケストレーションのインスタンスの情報を表示する方法](http://go.microsoft.com/fwlink/?LinkId=154855)(http://go.microsoft.com/fwlink/?LinkId=154855)。|  
|すべてのアクティブ、退避済み、および中断されたインスタンスが完了したら、アプリケーションから元のオーケストレーションの展開を解除します。|[オーケストレーションをアプリケーションから削除する方法](http://go.microsoft.com/fwlink/?LinkId=154856)(http://go.microsoft.com/fwlink/?LinkId=154856)。|  
|必要に応じて、アプリケーションを実行する各コンピューターの GAC から元のアセンブリ バージョンをアンインストールします。|[GAC からアセンブリをアンインストールする方法](http://go.microsoft.com/fwlink/?LinkId=154857)(http://go.microsoft.com/fwlink/?LinkId=154857)。|  
  
## <a name="binding-to-receive-ports-and-locations"></a>受信ポートおよび場所へのバインド  
 新規作成する場合は、受信ポートおよびオーケストレーションの新しいバージョンの場所、単に新しいポートへのバインドと、新しい成果物の参加/開始通常は十分なです。 新しい受信場所を作成して、ポートは、通常優先のアプローチでは、自分のシナリオは、関連付けの数が処理する必要がありますで受信も長時間のオーケストレーションを使用している場合に特にです。 ここでないことができますを既存の再利用する受信ポート、または参加解除を実行します。 新しいポートを作成する場合、バックエンドと取引先システムで、この変更を処理するために可能であることを確認します。 それ以外の場合は、すべての実行時間の長いインスタンスをアップグレードする前に、最後に待機する必要があります。  
  
 既存のポートを使用する場合は、次の操作を行います。  
  
1.  既存のポートに新しいバージョンのオーケストレーションをバインドします。  
  
2.  古いバージョンのオーケストレーションを参加解除 (ただし停止されません)。  
  
3.  参加させ、新しいオーケストレーションのバージョンを開始します。  
  
    > [!NOTE]  
    >  手順 2 および 3 の 1 つのトランザクションを実行するのにスクリプトを使用するには、メッセージはするが不足していない手動クリックして間のサブスクリプションようにします。