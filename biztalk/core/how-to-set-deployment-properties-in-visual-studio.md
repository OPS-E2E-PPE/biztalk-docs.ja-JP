---
title: "Visual Studio での展開のプロパティを設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2c6752e-c50d-4dd0-ac07-bf36ca10559c
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f448ec0569d64a3b3a14738bf08e68e083b80f0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-set-deployment-properties-in-visual-studio"></a>Visual Studio で展開プロパティを設定する方法
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] から BizTalk アプリケーションにソリューションを展開するには、まずプロジェクトのプロパティを設定する必要があります。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のソリューションに複数のプロジェクトが含まれる場合は、プロジェクトごとに個別にプロパティを構成する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、ローカル ファイル システムへの読み取り/書き込みアクセス許可を持つアカウントでログオンする必要があります。 ローカル コンピューターの管理者アカウントには、このアクセス許可があります。  
  
### <a name="to-enable-project-deployment-in-configuration-manager"></a>プロジェクトの展開を構成マネージャーで有効にするには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]クリックして**ビルド**メイン メニューで、をクリックして**Configuration Manager**です。  
  
2.  チェック、**展開**開いているソリューションを配置する必要がある各プロジェクトのオプションです。  
  
### <a name="to-configure-project-properties"></a>プロジェクトのプロパティを構成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーのプロパティを構成し、プロジェクトを右クリックして**プロパティ**です。  
  
2.  クリックして、**展開**プロジェクト デザイナーのタブです。  
  
3.  次の表に示すようにプロジェクトのプロパティを構成し、をクリックして**OK**です。  
  
4.  ソリューションの各プロジェクトごとに、手順 1. ～ 3. を繰り返します。  
  
    |プロパティ|値|説明|  
    |--------------|-----------|-----------------|  
    |Application Name|\<名前\>|このプロジェクトのアセンブリの展開先となる、BizTalk アプリケーションの名前。 アプリケーションが既に存在する場合、プロジェクトを展開すると、アセンブリがアプリケーションに追加されます。 アプリケーションが存在しない場合は、アプリケーションが新しく作成されます。 このフィールドを空白にした場合、アセンブリは、現在のグループの既定の BizTalk アプリケーションに展開されます。 スペースが含まれる名前は、二重引用符 (") で囲む必要があります。|  
    |構成データベース|\<BizTalk 管理データベース名\>|グループの BizTalk 管理データベースの名前。既定では BizTalkMgmtDb です。|  
    |[サーバー]|\<サーバー名\>|ローカル コンピューターで BizTalk 管理データベースをホストする SQL Server インスタンスの名前。 単一のコンピューターにインストールする場合、通常はローカル コンピューターの名前です。 **注:** BizTalk プロジェクトを別のコンピューターに移動する場合はおそらく必要がありますアセンブリを配置することができます前に、新しいコンピューター名を反映するようにサーバー プロパティを変更します。|  
    |再配置します。|True または False|これを True に設定すると (既定)、バージョン番号を変更せずに BizTalk アセンブリを再展開できます。|  
    |[グローバル アセンブリ キャッシュにインストール]|True または False|これを True に設定すると (既定)、アプリケーションのインストール時に、ローカル コンピューター上のグローバル アセンブリ キャッシュ (GAC) にアセンブリがインストールされます。 gacutil などの他のツールをインストールに使用する場合にのみ、このプロパティを False に設定します。|  
    |ホスト インスタンスを再起動します|True または False|これを True に設定すると、アセンブリの再展開時に、ローカル コンピューター上で実行中のすべてのホスト インスタンスが自動的に再起動されます。 False に設定した場合 (既定)、アセンブリの再展開時に、ホスト インスタンスを手動で再起動する必要があります。 **注:**ソリューション レベルからアセンブリを再デプロイする場合は、ホスト インスタンスが再起動されますがこのオプションを True に設定するプロジェクトごとにします。 結果として、再起動が 2 回以上行われる可能性があります。 ソリューション レベルからの再展開を計画する場合は、ソリューション内のただ 1 つのプロジェクトに対してこのプロパティを True に設定することで、ホスト インスタンスが複数回再起動することを防ぐことができます。 その場合は、ソリューション内で再展開される最後のプロジェクトに設定する必要があります。 また、再展開を実行するときにホスト インスタンスが停止された場合は、起動されません。|  
    |単体テストを有効にする|True または False|プロジェクトの単体テストを有効にするかどうかを指定します。|  
  
## <a name="see-also"></a>参照  
 [Visual Studio から BizTalk アプリケーションへの BizTalk アセンブリの展開](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)