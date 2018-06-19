---
title: 'シナリオ: 新しいアプリケーションの展開 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, applications
- applications, deploying
- deploying [applications], examples
- applications, examples
- examples, deploying
ms.assetid: 6d34a626-9fd4-4c33-a067-b66333eec01f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 938767237d21b74829c786bdd5d57c7d9df15c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269210"
---
# <a name="scenario-deploying-a-new-application"></a>新しいアプリケーションの展開シナリオ。
このトピックでは、これまで展開したことのない新しい環境にアプリケーションを展開するシナリオについて説明します。たとえば、ステージング環境で構成済みのアプリケーションを実稼働環境に展開する場合などです。  
  
 」の説明に従って[、アプリケーションの展開プロセス](../core/the-application-deployment-process.md)間、1 つの環境からアプリケーションを移動するときに、アプリケーションの .msi ファイルにエクスポートします。 その後、新しい環境で BizTalk グループに .msi ファイルをインポートします。 また、アプリケーションを実行するグループ内のコンピューターに、アプリケーションをインストールします。 アプリケーションが機能するためには、アプリケーションを実行する各コンピューターにインストールしてからアプリケーションを起動する必要があります。  
  
 次の図では、アプリケーション 1 が .msi ファイルから BizTalk グループ B にインポートされます。  
  
 ![BizTalk アプリケーションを配置する](../core/media/deployapplication.gif "DeployApplication")  
  
 これにより、以下のようにアイテムがさまざまな BizTalk Server データベースにインポートされます。  
  
-   BizTalk アセンブリ、.NET アセンブリ、バインド、バインド ファイル、BAM テンプレート、COM コンポーネント、証明書、テキスト ファイルは、すべて BizTalk 管理データベースに追加されます。  
  
-   ポリシーとボキャブラリは、ルール エンジン データベースに追加されます。  
  
-   BAM テンプレートと BAM 定義ファイルは、どちらも BAM プライマリ インポート データベースに追加されます。  
  
 また、これらの各アイテムは、BizTalk 管理データベース内でアプリケーション 1 に関連付けられます。  
  
 ローカル コンピューターにも、.msi ファイルからアプリケーションをインストールします。 これにより、以下のように .msi ファイルに格納されているさまざまなアイテムがインストールされます。  
  
-   VirtualDirectory という名前の仮想ディレクトリが、インターネット インフォメーション サービス (IIS) メタベース内に作成されます。  
  
-   証明書がローカル証明書ストアに追加されます。  
  
-   テキスト ファイルと COM コンポーネントが、ローカル ファイル システムにコピーされます。  
  
-   BizTalk アセンブリと .NET アセンブリが、グローバル アセンブリ キャッシュ (GAC) に追加されます (この展開オプションが選択された場合)。  
  
-   .NET アセンブリと COM コンポーネントが、Windows レジストリに追加されます (この展開オプションが選択された場合)。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開と管理のシナリオ](../core/application-deployment-and-management-scenarios.md)   
 [BizTalk アプリケーションの展開](../core/deploying-biztalk-applications.md)