---
title: カスタマイズ用の新しい管理パックの作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ce1ffa0-57c7-41ce-b459-48c36522889e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d04b29cd96a66057d83b5212472f0ea69150f0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297594"
---
# <a name="create-a-new-management-pack-for-customizations"></a>カスタマイズ用の新しい管理パックを作成します。
ほとんどのベンダーの管理パックは、管理パック ファイルの元の設定のいずれかを変更できないようににシールされます。 ただし、上書き、新しい監視オブジェクトなどのカスタマイズを作成し、それらを別の管理パックに保存することができます。 既定では、Operations Manager 2007 R2 または 2012 はすべてのカスタマイズを既定の管理パックに保存されます。 ベスト プラクティスとしては、代わりにカスタマイズする封印された管理パックごとの個別の管理パックを作成する必要があります。  
  
 上書きを格納する新しい管理パックを作成することにより、次の利点を得ることができます。  
  
-   テスト環境や運用前の環境で作成したカスタマイズを運用環境にエクスポートするプロセスが簡単になります。 たとえば、複数の管理パックのカスタマイズを含む既定の管理パックをエクスポートする代わりに、1 つの管理パックのカスタマイズを含む管理パックだけをエクスポートできます。  
  
-   既定の管理パックを削除することがなく元の管理パックを削除することができます。 カスタマイズを含む管理パックは、元の管理パックに依存します。 この依存関係のため、カスタマイズを含む管理パックを先に削除しないと、元の管理パックは削除できません。 すべてのカスタマイズについては、既定の管理パックに保存する場合は、元の管理パックを削除する前に、既定の管理パックを削除する必要があります。  
  
-   個々の管理パックに対するカスタマイズの追跡および更新が簡単になります。  
  
 詳細については約封印された管理パックの封印されていない、参照してください。[管理パックの形式](http://go.microsoft.com/fwlink/?LinkID=198193)(http://go.microsoft.com/fwlink/?LinkId=198193)。 管理パックのカスタマイズの詳細については、次を参照してください。[管理パックのカスタマイズ](http://go.microsoft.com/fwlink/?LinkID=198194)(http://go.microsoft.com/fwlink/?LinkID=198194)。