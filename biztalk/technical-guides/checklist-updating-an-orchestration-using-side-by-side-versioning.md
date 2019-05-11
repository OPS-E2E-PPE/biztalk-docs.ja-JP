---
title: チェックリスト:サイド バイ サイド バージョン管理を使用してオーケストレーションの更新 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 97f66987-0269-4dfe-a648-7b68412e86fe
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd8c0f9e1424982324aff88115188b9d6a74f835
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397086"
---
# <a name="checklist-updating-an-orchestration-using-side-by-side-versioning"></a>チェックリスト:サイド バイ サイド バージョン管理を使用してオーケストレーションを更新しています
オーケストレーションへの変更は他にも、マップなどの成果物への変更よりも複雑にすることはできます。 有効期間が短いオーケストレーションがあれば、単純な更新は十分であります。 実行時間の長いオーケストレーションまたは既存のインスタンスを終了することはできませんがある場合は、サイド バイ サイド バージョン管理が唯一の選択肢はなります。  
  
 オーケストレーションでは、実行時間の長いトランザクションを処理するときにすぐに更新されたバージョンのオーケストレーションを変更できません。 元のバージョンが失われないように、メッセージの処理が完了するを許可する必要があります。 これを行うには、元の 1 つとして、同じアプリケーションに更新されたオーケストレーションを展開します。 元のバージョンを停止し、以前のバージョンがインフライト メッセージの処理を続行中には、すべての新しいメッセージを受信するように、更新されたバージョンを開始します。 元のオーケストレーションは、そのすべてのメッセージの処理が終了したらが展開された BizTalk アプリケーションから解除します。  
  
|手順|リファレンス|  
|-----------|---------------|  
|オーケストレーションに必要な変更を行った後は、アセンブリのバージョン番号をインクリメントします。|[アセンブリを更新する方法](../technical-guides/how-to-update-an-assembly.md)|  
|Visual Studio から BizTalk アプリケーションにアセンブリを展開して、アセンブリをテストします。 **注:** GAC にアセンブリをインストールする展開オプションを選択することを確認します。|[BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開](http://go.microsoft.com/fwlink/?LinkID=154719)(http://go.microsoft.com/fwlink/?LinkID=154719)します。|  
|.Msi ファイルに、テスト環境でのアプリケーションからアセンブリをエクスポートします。|[アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)|  
|.Msi ファイルを更新するオーケストレーションを含む実稼働環境で BizTalk アプリケーションにインポートします。 **注:** 次の手順を使用するには、運用環境に展開すると、アセンブリをテストします。|[.msi ファイルのアプリケーションをインポートする方法](../technical-guides/how-to-import-an-application-from-an-msi-file.md)|  
|元のオーケストレーションとして同じバインディングを使用して、更新されたオーケストレーションをバインドします。|[オーケストレーションのバインドを構成する方法](http://go.microsoft.com/fwlink/?LinkId=154850)(http://go.microsoft.com/fwlink/?LinkId=154850)します。|  
|元のオーケストレーションの参加を解除し、更新されたオーケストレーションを開始します。 **注:** メッセージの消失を回避するには、必要がありますこれを行うプログラムを使用します。|プログラムによって、オーケストレーションの展開に関する詳細については、次を参照してください。[展開とプログラム、オーケストレーションの新しいバージョンを開始](http://go.microsoft.com/fwlink/?LinkId=154851)(http://go.microsoft.com/fwlink/?LinkId=154851)します。<br /><br /> オーケストレーションを手動で展開の詳細については、BizTalk Server ヘルプでは、次を参照してください。<br /><br /> -   [オーケストレーションを参加解除する方法](http://go.microsoft.com/fwlink/?LinkId=154852)(http://go.microsoft.com/fwlink/?LinkId=154852)します。<br />-   [オーケストレーションを参加させる方法](http://go.microsoft.com/fwlink/?LinkId=154853)(http://go.microsoft.com/fwlink/?LinkId=154853)します。<br />-   [オーケストレーションを開始する方法](http://go.microsoft.com/fwlink/?LinkId=154854)(http://go.microsoft.com/fwlink/?LinkId=154854)します。|  
|システムの監視、グループのハブを使用して元のオーケストレーションのバージョンのインスタンスがクエリ ビュー ページします。|[オーケストレーションのインスタンス情報を表示する方法](http://go.microsoft.com/fwlink/?LinkId=154855)(http://go.microsoft.com/fwlink/?LinkId=154855)します。|  
|すべてのアクティブ、退避済み、および中断されたインスタンスが完了したら、アプリケーションから元のオーケストレーションの展開を解除します。|[オーケストレーションをアプリケーションから削除する方法](http://go.microsoft.com/fwlink/?LinkId=154856)(http://go.microsoft.com/fwlink/?LinkId=154856)します。|  
|必要に応じて、アプリケーションを実行している各コンピューターの GAC から元のアセンブリ バージョンをアンインストールします。|[GAC からアセンブリをアンインストールする方法](http://go.microsoft.com/fwlink/?LinkId=154857)(http://go.microsoft.com/fwlink/?LinkId=154857)します。|  
  
## <a name="binding-to-receive-ports-and-locations"></a>受信ポートと受信場所へのバインド  
 新規作成する場合は、受信ポートおよびオーケストレーションの新しいバージョンの場所、単に新しいポートにバインドしへの参加以降、新しい成果物は、通常ための十分です。 新しい受信場所を作成して、ポートは、通常、優先のアプローチでは、実際のシナリオは、数の関連付けが処理する必要があるで受信も実行時間の長いオーケストレーションを使用している場合に特にします。 この場合、しないことができますを既存の再利用する受信ポートまたは参加解除を実行します。 新しいポートを作成する場合は、この変更を処理するために、バックエンドとパートナーのシステムの可能性があることを確認します。 有効でない場合は、すべての実行時間の長いインスタンスをアップグレードする前に、最後に待機する必要があります。  
  
 既存のポートを使用する場合は、次の操作を行います。  
  
1.  オーケストレーションの新しいバージョンを既存のポートにバインドします。  
  
2.  以前のバージョンのオーケストレーションを参加解除 (ただし停止しません)。  
  
3.  参加させ、新しいオーケストレーションのバージョンを開始します。  
  
    > [!NOTE]  
    >  手順 2 および 3 の 1 つのトランザクションを実行するのにスクリプトを使用するには、メッセージが手動クリックして間のサブスクリプションを欠落していないができるようにします。