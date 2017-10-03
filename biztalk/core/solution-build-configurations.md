---
title: "ソリューション ビルド構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Configuration Manager
- building, solutions
- building, Configuration Manager
- solutions, deploying
- deploying, building
- solutions, developing
- solutions, build configuration
ms.assetid: 6f2cce47-388d-4c93-9146-768f53b8207e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e537ca4bc2dd85722ddf3afd4eaba443aab7a25b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="solution-build-configurations"></a>ソリューション ビルドの構成
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でビルドする他のプロジェクトと同様に、構成マネージャーを使用して、ソリューション ビルドの構成を指定できます。 ソリューション ビルド構成を使用すると、ソリューションのビルドでどのプロジェクトに含めると、それを展開するかどうかを決定できます。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]両方をサポート**デバッグ**と**リリース**の構成をビルドします。  
  
 ソリューション ビルド構成のチェック マークと、**ビルド**列を使用するソリューションを構築してが完了したら、アセンブリを生成します。 チェック マークはでもある場合、**展開**プロジェクト デザイナーでの展開設定に基づいて、列からアプリケーションが展開されます。  
  
 Configuration Manager と構成の完全なリファレンス [オプション] ダイアログ ボックスでボックスにある次のリファレンス リンク提供: [http://go.microsoft.com/fwlink/?LinkId=125365](http://go.microsoft.com/fwlink/?LinkId=125365)です。  
  
### <a name="to-configure-build-properties-in-configuration-manager"></a>構成マネージャーでビルド プロパティを設定するには  
  
1.  **[ビルド]** メニューの **[構成マネージャー]**をクリックします。  
  
2.  **Configuration Manager**ダイアログ ボックスで、ビルド プロパティを構成するには次のいずれかを選択します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**Configuration**|選択**リリース**または**デバッグ**プロジェクトの構成。 または、新しい構成を作成するか、既存の構成を編集します。|  
    |**プラットフォーム**|コンパイルしたアセンブリの CPU アーキテクチャを表す、プロジェクトのプラットフォームを選択します。 または、新しいプラットフォームを作成するか、既存のプラットフォームを編集します。|  
    |**ビルド**|プロジェクトをビルドするか、ソリューションのビルド コマンドに対応してリビルドするには、プロジェクトのこの列のチェック ボックスをオンにします。|  
    |**配置**|ソリューションまたはプロジェクトに対してビルド コマンドが実行されたときにプロジェクトを展開設定に基づいて展開するには、この列のチェック ボックスをオンにします。|  
  
## <a name="see-also"></a>参照  
 [Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)   
 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)