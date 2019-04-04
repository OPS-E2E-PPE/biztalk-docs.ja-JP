---
title: カスタマイズの新しい管理パックの作成 |Microsoft Docs
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
ms.openlocfilehash: 3108696e89e6a411049c11929c8e7dcb7f48db34
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016799"
---
# <a name="create-a-new-management-pack-for-customizations"></a>カスタマイズの新しい管理パックを作成します。
管理パック ファイルの元の設定のいずれかを変更できないように、ほとんどのベンダー管理パックをシールされています。 ただし、オーバーライドや新しい監視オブジェクトなどのカスタム設定を作成して、別の管理パックに保存することができます。 既定では、Operations Manager 2007 R2 または 2012 はすべてのカスタマイズを既定の管理パックに保存されます。 ベスト プラクティスとしては、代わりにカスタマイズする封印された管理パックごとの個別の管理パックを作成する必要があります。  
  
 オーバーライドを格納するための新しい管理パックの作成には、以下のような利点があります。  
  
- テスト環境や運用前の環境で作成したカスタマイズを運用環境にエクスポートするプロセスが簡単になります。 たとえば、複数の管理パックのカスタマイズを含む既定の管理パックをエクスポートする代わりに、1 つの管理パックのカスタマイズを含む管理パックだけをエクスポートできます。  
  
- 既定の管理パックを削除することがなく元の管理パックを削除することができます。 カスタマイズを含む管理パックは、元の管理パックに依存します。 この依存関係のため、カスタマイズを含む管理パックを先に削除しないと、元の管理パックは削除できません。 すべてのカスタマイズについては、既定の管理パックに保存する場合は、元の管理パックを削除する前に、既定の管理パックを削除する必要があります。  
  
- 個々の管理パックに対するカスタマイズの追跡および更新が簡単になります。  
  
  シールし、封印されていない管理パックについての詳細についてを参照してください。[管理パックの形式](http://go.microsoft.com/fwlink/?LinkID=198193)(http://go.microsoft.com/fwlink/?LinkId=198193)します。 管理パックのカスタマイズの詳細については、[管理パックのカスタマイズ](http://go.microsoft.com/fwlink/?LinkID=198194)(http://go.microsoft.com/fwlink/?LinkID=198194)を参照してください。