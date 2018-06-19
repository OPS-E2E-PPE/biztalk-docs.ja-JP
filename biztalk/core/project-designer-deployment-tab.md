---
title: 'プロジェクト デザイナー: [展開] タブ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- properties, Configuration database [BizTalk Server]
- Redeploy property
- configuration properties [deployment], Server property
- Server property
- configuration properties [deployment], Install to Global Assembly Cache (GAC) property
- properties, Management database
- Install to Global Assembly Cache (GAC) property
- Configuration database [BizTalk Server], properties
- Management database, properties
- Administration Group property
- configuration properties [deployment], Redeploy property
- configuration properties [deployment], Management database property
- configuration properties [deployment], Administration Group property
ms.assetid: 5b64f99c-4ec6-4ed3-8590-46420e2f75b8
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 972f3956a19d66d47238ee8170584b4faf6ba886
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264946"
---
# <a name="project-designer-deployment-tab"></a>プロジェクト デザイナー: [展開] タブ
**展開**プロジェクト デザイナーの [プロパティ] タブでは、BizTalk プロジェクトの配置の属性を構成することができます。 両方を構成する必要があります、**サーバー**と**構成データベース**(BizTalk 管理データベースとも呼ばれます) 展開を成功させるのに設定されるプロパティです。  
  
## <a name="application-name"></a>Application Name  
 アセンブリの展開先となる BizTalk アプリケーションを指定します。 このフィールドを空にした場合、このプロジェクトは既定のアプリケーションに展開されます。  
  
## <a name="configuration-database"></a>構成データベース  
 このフィールドでは、展開されたアセンブリに対して使用する BizTalk 構成データベースの名前を指定します。 BizTalk プロジェクトを展開プロジェクトとして構成した場合に必要となります。  
  
> [!NOTE]
>  BizTalk 構成データベースは BizTalk 管理データベースとも呼ばれます。  
  
 既定の構成データベース名は、BizTalkMgmtDb です。  
  
## <a name="server"></a>[サーバー]  
 ここには、[構成] リポジトリ (BizTalk 管理データベースまたは構成データベース) が配置されているサーバーの名前を指定します。 BizTalk プロジェクトを "展開" として構成した場合、BizTalk プロジェクトをこのサーバーに展開します。  
  
## <a name="redeploy"></a>再配置します。  
 使用する、**再展開**プロパティを既存の構成を削除して、アセンブリを配置するたびに、構成を再作成するかどうかを判断します。 既定値は`True`します。  
  
## <a name="install-to-global-assembly-cache"></a>[グローバル アセンブリ キャッシュにインストール]  
 使用する、**グローバル アセンブリ キャッシュにインストール**プロパティを指定する場合を[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールする必要があります。  
  
## <a name="restart-host-instances"></a>ホスト インスタンスを再起動します  
 設定した場合**ホスト インスタンスを再起動します**に**True**、によって、プロジェクトを配置するときに、ローカル コンピューター上のホスト インスタンスが再起動されます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。 この設定は、開発サイクルで、変更を行う場合や頻繁に再展開を実行する場合に役立ちます。この設定を使用すると、関連するホスト インスタンスを手動で再起動する必要がなくなります。  
  
 関連するホスト インスタンスを再起動しない場合、BizTalk アプリケーションに最新の変更が反映されないことがあります。これは、変更前の内容がキャッシュに残っている可能性があるためです。 ホスト インスタンスを再起動すると、キャッシュされたアセンブリは削除されます。  
  
## <a name="enable-unit-testing"></a>単体テストを有効にする  
 プロジェクトの単体テストを有効にするかどうかを指定しました。  
  
## <a name="see-also"></a>参照  
 [Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)   
 [BizTalk プロジェクトのプロパティ ウィンドウ](../core/biztalk-project-properties-window.md)