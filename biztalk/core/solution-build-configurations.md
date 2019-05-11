---
title: ソリューション ビルドの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e67898e3e24b98f9efbe92494e0f7fbe28b2fba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244310"
---
# <a name="solution-build-configurations"></a>ソリューション ビルドの構成
他のプロジェクトで作成すると同様[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューションのビルド構成を指定する Configuration Manager を使用することができます。 ソリューション ビルドの構成に含めるには、どのプロジェクトがソリューションのビルドし、それを展開するかどうかを決定できます。 BizTalk Server は両方ともサポート**デバッグ**と**リリース**の構成をビルドします。  
  
 ソリューション ビルド構成にあるチェック マークで、**ビルド**列を使用するソリューションを構築してが完了したら、アセンブリを生成します。 チェック ボックスもオンにする場合、**デプロイ**プロジェクト デザイナーでの展開設定に基づいて、列で、そのアプリケーションがデプロイされます。  
  
 Configuration Manager と、構成への参照を完全なオプション ダイアログ ボックスでボックスにある次の参照リンクの提供: [ http://go.microsoft.com/fwlink/?LinkId=125365](http://go.microsoft.com/fwlink/?LinkId=125365)します。  
  
### <a name="to-configure-build-properties-in-configuration-manager"></a>Configuration Manager でのビルド プロパティを構成するには  
  
1.  **[ビルド]** メニューの **[構成マネージャー]** をクリックします。  
  
2.  **Configuration Manager**ダイアログ ボックスで、ビルド プロパティを構成するには次のいずれかを選択します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**Configuration**|選択**リリース**または**デバッグ**プロジェクトの構成。 新しい構成を作成または、既存のものを編集します。|  
    |**プラットフォーム**|プロジェクトのコンパイル済みアセンブリの CPU アーキテクチャを表すためのプラットフォームを選択します。 新しいプラットフォームを作成または、既存のものを編集します。|  
    |**ビルド**|プロジェクトのプロジェクトを作成またはソリューションのビルド コマンドへの応答で再作成するには、この列のボックスを確認します。|  
    |**配置**|デプロイ プロジェクトがある場合は、この列のボックスは、ソリューションまたはプロジェクトのビルド コマンドが発行されたときに展開の設定に基づく確認してください。|  
  
## <a name="see-also"></a>参照  
 [Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)   
 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)