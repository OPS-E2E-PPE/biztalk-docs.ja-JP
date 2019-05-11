---
title: シナリオ:新しいアプリケーションの展開 |Microsoft Docs
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
ms.openlocfilehash: 932f8e8692b3f0d2061550bebbc7faf7a8175b2e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308575"
---
# <a name="scenario-deploying-a-new-application"></a>シナリオ:新しいアプリケーションの展開
このトピックでは、どこに展開されていない; の前に、新しい環境にアプリケーションのデプロイのシナリオを説明しますたとえば、運用環境にステージング環境で構成されているアプリケーションを展開します。  
  
 」の説明に従って[、アプリケーションの展開プロセス](../core/the-application-deployment-process.md)する間、1 つの環境からアプリケーションを移動する場合は、.msi ファイルにアプリケーションをエクスポートします。 .Msi ファイルをインポートするには、新しい環境での BizTalk グループにします。 また、アプリケーションをインストールするには、アプリケーションを実行しているそのグループ内のコンピューターにします。 機能する、前に実行され、アプリケーションを起動する各コンピューターにアプリケーションをインストールする必要があります。  
  
 次の図では、Application1 は BizTalk グループ B にインポートを .msi ファイルからは、  
  
 ![BizTalk アプリケーション展開](../core/media/deployapplication.gif "DeployApplication")  
  
 とおり: さまざまな BizTalk Server データベースにアイテムをインポートこれ  
  
- BizTalk アセンブリ、.NET アセンブリ、バインド、バインド ファイル、BAM テンプレート、COM コンポーネント、証明書、およびテキスト ファイルはすべて BizTalk 管理データベースに追加します。  
  
- ポリシーとボキャブラリは、ルール エンジン データベースに追加されます。  
  
- BAM テンプレートと BAM 定義ファイル、BAM プライマリ インポート データベースに追加されます。  
  
  これらの各アイテムも Application1 BizTalk 管理データベースに関連付けします。  
  
  アプリケーションは、.msi ファイルからローカル コンピューターにもインストールされます。 これには、次のように、.msi ファイルに含まれるさまざまな成果物がインストールされます。  
  
- VirtualDirectory という名前の仮想ディレクトリは、インターネット インフォメーション サービス (IIS) メタベースに作成されます。  
  
- 証明書は、ローカル証明書ストアに追加されます。  
  
- テキスト ファイルと COM コンポーネントは、ローカル ファイル システムにコピーされます。  
  
- この展開オプションは、それらの選択した場合、BizTalk アセンブリと .NET アセンブリがグローバル アセンブリ キャッシュ (GAC) に追加されます。  
  
- .NET アセンブリと COM コンポーネントは、それらの配置オプションを選択した場合、Windows レジストリに追加されます。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開と管理のシナリオ](../core/application-deployment-and-management-scenarios.md)   
 [BizTalk アプリケーションの展開](../core/deploying-biztalk-applications.md)