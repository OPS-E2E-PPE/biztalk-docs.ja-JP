---
title: 'シナリオ: 複数のコンピューター間でのアイテムの分散 |Microsoft ドキュメント'
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
ms.openlocfilehash: abedc60ad13c7e8b2be3ce4caa7b8d34262b4e5c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269162"
---
# <a name="scenario-distributing-artifacts-among-multiple-computers"></a>シナリオ: 複数のコンピューター間での成果物を配布します。
このトピックでは、アプリケーション内のアイテムを、別々のコンピューターに選択的にインストールする場合のアプリケーション展開シナリオについて説明します。 これを行うのは、アプリケーション内の特定のアセンブリまたはその他の種類のアイテムを、BizTalk グループ内の特定のコンピューターにのみインストールする場合です。 そのためには、アプリケーションに含まれているアイテムを、物理コンピューターに同時にインストールするアイテムに応じて、複数の .msi ファイルにエクスポートします。  
  
 次の図は、BizTalk グループ 1 の BizTalk 管理データベースにインポートする .msi ファイルを示します。 これにより、そのグループで、Order Processing アプリケーションとすべてのアイテムが作成されます。 アプリケーションのアイテムは、2 つの .msi ファイルに分けてエクスポートします。 一方の .msi ファイルは、Assembly1、Certificate1、および Script1 を含みます。 もう一方の .msi ファイルは、Assembly2、Script2、および VirtualDirectory1 を含みます。  
  
 両方の .msi ファイルは、BizTalk グループ 2 にインポートされます。 両方に所属するため、Order Processing アプリケーションは、新しいグループの注文処理をという同じアプリケーションに両方の .msi ファイル内の成果物のすべてインポートされます。  
  
 また、アプリケーションのアイテムは、.msi ファイルから、グループ内でアイテムを実行するコンピューターにインストールされます。 仮想ディレクトリが格納されている .msi ファイルは BizTalk Server B および BizTalk Server C にインストールされます (両方が IIS を実行しています)。  
  
 ![別のコンピューターにインストールされている成果物](../core/media/distributionofartifacts.gif "DistributionOfArtifacts")  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開と管理のシナリオ](../core/application-deployment-and-management-scenarios.md)   
 [BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)   
 [BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)   
 [BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)