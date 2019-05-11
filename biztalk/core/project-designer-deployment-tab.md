---
title: プロジェクト デザイナー:[展開] タブ |Microsoft Docs
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
ms.openlocfilehash: b6cf82e112834dbacc021e3ce5564866a2e8cbbb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395616"
---
# <a name="project-designer-deployment-tab"></a>プロジェクト デザイナー:[展開] タブ
**展開**プロジェクト デザイナーの [プロパティ] タブを使用する BizTalk プロジェクトの展開属性を構成できます。 両方を構成する必要があります、 **Server**と**構成データベース**(BizTalk 管理データベースとも呼ばれます) の展開を正常に行う一連のプロパティ。  
  
## <a name="application-name"></a>Application Name  
 アセンブリを展開する BizTalk アプリケーションを指定します。 これが空の場合は、既定のアプリケーションに、プロジェクトに展開されています。  
  
## <a name="configuration-database"></a>構成データベース  
 展開済みのアセンブリを BizTalk 構成データベースの名前を指定するのにには、このフィールドを使用します。 これには、展開プロジェクトとして BizTalk プロジェクトを構成している場合は適用されます。  
  
> [!NOTE]
>  BizTalk 構成データベースは、BizTalk 管理データベースとも呼ばれます。  
  
 既定の構成データベース名には、BizTalkMgmtDb です。  
  
## <a name="server"></a>[サーバー]  
 これは、構成リポジトリ (BizTalk 管理または構成データベースとも呼ばれます) が配置されているサーバーの名前です。 "Deployment"として BizTalk プロジェクトを構成する場合、このサーバーに BizTalk プロジェクトを配置します。  
  
## <a name="redeploy"></a>再デプロイする.  
 使用する、**再デプロイ**プロパティを既存の構成を削除して、アセンブリを配置するたびに、構成を再作成するかどうかを判断します。 既定値は `True` です。  
  
## <a name="install-to-global-assembly-cache"></a>[グローバル アセンブリ キャッシュにインストール]  
 使用する、**グローバル アセンブリ キャッシュにインストール**プロパティを指定する場合を[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールする必要があります。  
  
## <a name="restart-host-instances"></a>ホスト インスタンスを再起動します。  
 設定した場合**ホスト インスタンスを再起動**に**True**、によって、プロジェクトが配置されると、ローカル コンピューター上のホスト インスタンスが再起動されます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。 これは変更を加えると、頻繁に再展開; するは、開発サイクル中に便利です。関連するホスト インスタンスを手動で再起動することはありません。  
  
 関連するホスト インスタンスを再起動しないと場合、最新の変更可能性がありますが反映されません、BizTalk アプリケーションで、以前のバージョンがキャッシュに残っているため。 キャッシュされたアセンブリを削除するホスト インスタンスを再起動します。  
  
## <a name="enable-unit-testing"></a>単体テストを有効にする  
 プロジェクト用の単体テストを有効にするかどうかを指定します。  
  
## <a name="see-also"></a>参照  
 [Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)   
 [BizTalk プロジェクトのプロパティ ウィンドウ](../core/biztalk-project-properties-window.md)