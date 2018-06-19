---
title: 'シナリオ: 次の 2 つのバージョンのアプリケーションを展開する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, multiple assemblies
- assemblies, multiple assemblies
- receive locations, examples
- assemblies, deploying
- assemblies, examples
ms.assetid: 3e79a7df-bf77-4a0b-86ec-359fcf3489b3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1bb4f04e8b00dd171de89bbed6f01d2a2d1e2e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268938"
---
# <a name="scenario-deploying-two-versions-of-an-application"></a>シナリオ: 次の 2 つのバージョンのアプリケーションを展開します。
ここでは、BizTalk グループ内にアプリケーションの 2 つのバージョンを展開して、両方のバージョンを同時に実行できるようにするためのシナリオを説明します。 このシナリオでは、アプリケーションの新しいメジャー バージョンを展開する必要があります。 これには、スキーマまたはプロトコルの変更 (事実上、新しいアプリケーションへの変更) が生じるため、パートナーはシステムとの通信方法を変更する必要があります。 このシステムの切り替えはテスト済みですが、完全な運用システム規模ではテストされていません。 パートナーの 20% で新しいシステムをテストし、すべてのパートナーがそのシステムを使用するようになるまでその比率を徐々に増やしていくことができます。  
  
 2 つのアプリケーションは 2 つの異なる受信場所でメッセージを受信するため、アプリケーションの新しいバージョンを使用して新しい URL にメッセージを送信し、新しいバーションでメッセージを処理するように、パートナーに依頼する必要があります。  
  
 次の図は、標準のアプリケーション並列展開を示しています。  
  
 ![2 つのアセンブリ バージョンを同時展開](../core/media/sidebysideassemblyversions.gif "SideBySideAssemblyVersions")  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開と管理のシナリオ](../core/application-deployment-and-management-scenarios.md)