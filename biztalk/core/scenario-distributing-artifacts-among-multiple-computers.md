---
title: シナリオ:複数のコンピューター間でのアイテムの分散 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying [artifacts], multiple computers
- examples, distributing
- examples, artifacts
- artifacts, distributing
- artifacts, examples
- deploying [artifacts], examples
- examples, deploying
ms.assetid: 7000cded-1fda-4276-b7f3-3f427f686f64
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e64cdf9ac474697961d4f8fd41bb75057d27aa54
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308319"
---
# <a name="scenario-distributing-artifacts-among-multiple-computers"></a>シナリオ:複数のコンピューター間でのアイテムを配布します。
このトピックではアプリケーションでアイテムが選択的に別のコンピューターにインストールされているアプリケーションの展開シナリオについて説明します。 特定のアセンブリまたはその他の種類の BizTalk グループ内の特定のコンピューターにのみインストールするアプリケーションでアイテムをする場合は、これを行う可能性があります。 これを行うには、これに基づいてアイテムをまとめてインストール、物理コンピューター上の複数の .msi ファイルにアプリケーションに含まれるアイテムをエクスポートできます。  
  
 次の図は、BizTalk グループ 1 の BizTalk 管理データベースにインポートする .msi ファイルを示します。 これにより、そのグループの Order Processing アプリケーションとすべてのアーティファクトが作成されます。 アプリケーションのアイテムは、2 つの複数の .msi ファイルにエクスポートされます。 1 つの .msi ファイルには、Assembly1、Certificate1、および Script1 が含まれています。 その他の .msi ファイルには、Assembly2、Script2、および virtualdirectory1 を含みますが含まれています。  
  
 両方の .msi ファイルは、BizTalk グループ 2 にインポートされます。 どちらも Order Processing アプリケーションに属している、ために、注文処理をという新しいグループに同じアプリケーションに両方の .msi ファイル内の成果物のすべてインポートされます。  
  
 さらに、アプリケーションのアイテムは、それらを実行するグループ内のコンピューターに .msi ファイルからインストールされます。 どちらも IIS を実行している BizTalk Server B および BizTalk Server C に仮想ディレクトリを含む .msi ファイルがインストールされていることに注意してください。  
  
 ![別のコンピューターにインストールされている成果物](../core/media/distributionofartifacts.gif "DistributionOfArtifacts")  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開と管理のシナリオ](../core/application-deployment-and-management-scenarios.md)   
 [BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)   
 [BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)   
 [BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)