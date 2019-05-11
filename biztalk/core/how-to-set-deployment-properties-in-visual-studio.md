---
title: Visual Studio での展開のプロパティを設定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2c6752e-c50d-4dd0-ac07-bf36ca10559c
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be4adfcb8061b296fe8765b0cd910f92bc1db266
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383938"
---
# <a name="how-to-set-deployment-properties-in-visual-studio"></a>Visual Studio での展開のプロパティを設定する方法
ソリューションをデプロイする前に[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を BizTalk アプリケーションにプロジェクトのプロパティを最初に設定する必要があります。 ソリューションで場合、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]複数のプロジェクトが含まれていますに個別に各プロジェクトのプロパティを構成する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、ローカル ファイル システムの読み取り/書き込み権限を持つアカウントを使用してログオンする必要があります。 ローカル コンピューターの管理者アカウントには、このアクセス許可があります。  
  
### <a name="to-enable-project-deployment-in-configuration-manager"></a>Configuration Manager でのプロジェクトの配置を有効にするには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]クリックして**ビルド**メイン メニューをクリックし、 **Configuration Manager**します。  
  
2. チェック、**デプロイ**開いているソリューションから展開する必要がある各プロジェクトのオプション。  
  
### <a name="to-configure-project-properties"></a>プロジェクトのプロパティを構成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーのプロパティを構成し、プロジェクトを右クリックして**プロパティ**します。  
  
2. をクリックして、**展開**プロジェクト デザイナー タブ。  
  
3. 次の表に示すようにプロジェクトのプロパティを構成し、 **OK**します。  
  
4. ソリューションの各プロジェクトごとに、手順 1. ～ 3. を繰り返します。  
  
   |プロパティ|値|説明|  
   |--------------|-----------|-----------------|  
   |Application Name|\<名前\>|このプロジェクトのアセンブリの展開先となる、BizTalk アプリケーションの名前。 アプリケーションが既に存在する場合、プロジェクトを展開すると、アセンブリがアプリケーションに追加されます。 アプリケーションが存在しない場合は、アプリケーションが新しく作成されます。 このフィールドが空白の場合、アセンブリは、現在のグループで、既定の BizTalk アプリケーションに展開されます。 スペースが含まれる名前は、二重引用符 (") で囲む必要があります。|  
   |構成データベース|\<BizTalk 管理データベース名\>|グループの BizTalk 管理データベースの名前。既定では BizTalkMgmtDb です。|  
   |[サーバー]|\<サーバー名\>|ローカル コンピューターで BizTalk 管理データベースをホストする SQL Server インスタンスの名前。 単一のコンピューターにインストールする場合、通常はローカル コンピューターの名前です。 **注:** BizTalk プロジェクトを別のコンピューターに移動する場合する可能性がありますが、アセンブリを展開できる前に、新しいコンピューター名を反映するように、サーバーのプロパティを変更する必要があります。|  
   |再デプロイする.|True または False|これを True に設定すると (既定)、バージョン番号を変更せずに BizTalk アセンブリを再展開できます。|  
   |[グローバル アセンブリ キャッシュにインストール]|True または False|これを True (既定値) に設定インストール アセンブリ ローカル コンピューターのグローバル アセンブリ キャッシュ (GAC) にアプリケーションをインストールするときにします。 のみの場合は False に設定をこのインストールにより、gacutil などの他のツールを使用して行います。|  
   |ホスト インスタンスを再起動します。|True または False|これを True に設定すると、アセンブリの再展開時に、ローカル コンピューター上で実行中のすべてのホスト インスタンスが自動的に再起動されます。 False に設定した場合 (既定)、アセンブリの再展開時に、ホスト インスタンスを手動で再起動する必要があります。 **注:** ソリューション レベルからアセンブリを再デプロイする場合ホスト インスタンスがこのオプションを True に設定を持つ各プロジェクトの 1 回再起動されます。 結果として、再起動が 2 回以上行われる可能性があります。 ソリューション レベルからの再展開を計画する場合は、ソリューション内のただ 1 つのプロジェクトに対してこのプロパティを True に設定することで、ホスト インスタンスが複数回再起動することを防ぐことができます。 その場合は、ソリューション内で再展開される最後のプロジェクトに設定する必要があります。 また、再展開を実行するときにホスト インスタンスが停止された場合は、起動されません。|  
   |単体テストを有効にする|True または False|プロジェクトの単体テストを有効にするかどうかを指定します。|  
  
## <a name="see-also"></a>参照  
 [Visual Studio から BizTalk アプリケーションへの BizTalk アセンブリの展開](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)