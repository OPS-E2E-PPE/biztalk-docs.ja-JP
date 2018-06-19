---
title: ポリシーをエクスポートする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [policies], exporting
- policies, exporting
- exporting, policies
ms.assetid: 2e46d96a-7762-479b-be20-bd590b2a4f0a
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 752336e0642c42418f6c68ddefb719d02051d937
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254914"
---
# <a name="how-to-export-a-policy"></a>ポリシーをエクスポートする方法
ここでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、1 つ以上のポリシーと関連付けられたボキャブラリをエクスポートする方法について説明します。  
  
 ポリシーをエクスポートする際には、次の重要事項を念頭に置いてください。  
  
-   BizTalk Server 管理コンソールを使用すると、BizTalk グループまたは BizTalk アプリケーションからポリシーとボキャブラリのそれぞれをエクスポートすることができます。 BTSTask を使用すると、アプリケーションからポリシーをエクスポートすることができ、関連付けられているすべてのボキャブラリも同様にエクスポートされます。 エクスポートするボキャブラリを選択することはできません。  
  
    > [!IMPORTANT]
    >  管理コンソールを使用した場合は、エクスポートするボキャブラリを選択できます。 ポリシーに関連付けられているすべてのボキャブラリをエクスポートするよう選択することをお勧めします。 これにより、エクスポート先の環境に、必要なボキャブラリを確実に存在させることができます。 必要なボキャブラリが既にエクスポート先の環境に展開されていたとしても、関連付けられているポリシーが削除された場合は、ボキャブラリも同様に削除されます。 これは、ポリシーを削除すると、そのボキャブラリについても、別のポリシーで使用されている以外のものはすべて削除されるためです。  
  
-   できますし、インポートする、ポリシーを別の BizTalk グループまたは別の BizTalk グループ内のアプリケーションに」の説明に従って[ポリシーをインポートする方法](../core/how-to-import-a-policy.md)です。  
  
-   ポリシーをエクスポートするには、そのポリシーが BizTalk グループのルール エンジン データベースにあらかじめ存在している必要があります。 」の説明に従って、ポリシーをルール エンジン データベースにインポートするいくつかの方法がある[ポリシーをインポートする方法](../core/how-to-import-a-policy.md)です。  
  
    > [!NOTE]
    >  ルール エンジン展開ウィザードを使用してルール エンジン データベースからポリシーを削除すると、そのポリシーは、管理コンソールでは表示されたままになりますが、エクスポートすることはできなくなります。 ルール エンジン展開ウィザードの詳細については、次を参照してください。[展開と展開解除ポリシーとボキャブラリを方法](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)です。  
  
-   エクスポートに管理コンソールを使用する場合、ポリシーとボキャブラリは .xml ファイルにエクスポートされます。 エクスポートに BTSTask コマンド ライン ツールを使用する場合、ポリシーとボキャブラリはアプリケーションの .msi ファイルにエクスポートされます。  
  
-   BTSTask にはポリシーをエクスポートする専用のコマンドはありませんが、BTSTask の ExportApp コマンドを使用して、他のアイテムを含めずに目的のポリシーだけを選択的にエクスポートすることができます。 これにより、そのポリシーを含んだアプリケーションの .msi ファイルが生成されます。 ImportApp コマンドを使用して、その .msi ファイルを別の BizTalk グループにインポートできます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するための前提条件は、次のとおりです。  
  
-   BizTalk Server 管理者グループに属するアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
-   ビジネス ルール エンジンがインストールされている必要があります。 詳細については、次を参照してください。 [BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)です。  
  
-   エクスポートするポリシーが、BizTalk グループのルール エンジン データベースに存在している必要があります。 アプリケーションからポリシーをエクスポートする場合は、アプリケーションにも追加されている必要があります。  
  
## <a name="to-export-a-policy"></a>ポリシーをエクスポートするには  
  
#### <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**BizTalk グループを展開します。  
  
3.  すべての BizTalk グループを右クリックでポリシーをエクスポートするポリシーを選択する場合、**アプリケーション**フォルダーで、をクリックして**エクスポート**、順にクリック**ポリシー**です。  
  
     または  
  
     特定のアプリケーションでポリシーをエクスポートする場合は、アプリケーション フォルダーを展開し、アプリケーションを右クリックをクリックして**エクスポート**、クリックして**ポリシー**です。  
  
     または  
  
     ポリシーを含んでいる [ポリシー] フォルダーをクリックして特定のポリシーのみをエクスポートする場合をポリシーを右クリックし、をクリックして**エクスポート**です。  
  
4.  ポリシーのエクスポート] ページで、[**エクスポートするポリシー**、エクスポートするポリシーを選択します。  
  
5.  **をエクスポートするボキャブラリ**をエクスポートするボキャブラリのチェック ボックスを選択して、エクスポートしないボキャブラリのチェック ボックスをオフにします。 エクスポートするポリシーで使用されるボキャブラリは自動的に選択されます。  
  
6.  **をエクスポートするファイル**にポリシーまたはポリシーのエクスポート先を XML ファイルのパスを入力し、をクリックして**OK**です。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  /ResourceSpec オプションを使用するポリシーをエクスポートする」の説明に従って、BizTalk アプリケーションにアイテムを一覧表示する XML ファイルを生成する、BTSTask の ListApp コマンドを使用して[ListApp コマンド](../core/listapp-command.md)です。  
  
2.  前の手順で生成した XML ファイルを編集して、エクスポートするポリシー以外のアイテムをすべて削除します。  
  
3.  BTSTask の ExportApp コマンドを使用します。ここでは、/ResourceSpec パラメーターに変更後の XML ファイルを指定します。 詳細については、次を参照してください。 [ExportApp コマンド](../core/exportapp-command.md)です。  
  
     BTSTask によって、指定したポリシーとそれに関連付けられているすべてのボキャブラリがアプリケーションの .msi ファイルにエクスポートされます。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーション、バインド、およびポリシーをエクスポートします。](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [ポリシーの管理](../core/managing-policies.md)