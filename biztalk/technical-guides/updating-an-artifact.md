---
title: アイテムの更新 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40feab57-4286-4bdf-8f52-25d02b3fa60c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f32efa6195013d77ee368c0678a9ca67afb4e6e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980043"
---
# <a name="updating-an-artifact"></a>アイテムの更新
2 つ以上の BizTalk アプリケーションにおけるアイテム間の依存関係には、アプリケーションの展開と保守に大きな影響を及ぼすことができます。 成果物は、その成果物を適切に機能するために使用する必要があるとき、依存関係をたとえば、オーケストレーションが必要なメッセージを正しく送信するために特定のパイプラインを使用します。  
  
 アプリケーションのアイテムを更新するには、必要があります最初を展開解除する、それに依存するすべてのアーティファクトと共にします。 依存関係にあるアイテムが同じアプリケーション内に存在する場合、更新されるアイテムと依存するアイテムの展開解除タスクと再展開タスクが、BizTalk Server によって自動的に実行されます。 しかし、依存関係にあるアイテムが別のアプリケーションに存在する場合は、動作が異なります。 場合は 1 つのアプリケーション内のアイテムを更新して、それに依存している別のアプリケーション内のアイテム、解除して、依存するアイテムを次のように手動で再デプロイする必要があります。  
  
1. 依存するアイテムの停止、参加解除、およびバインド解除を行います。  
  
2. 依存先のアイテムを更新します。  
  
3. 依存するアイテムをバインドし、参加させ、開始します。  
  
   手動でアイテムを更新する手順を実行する必要を回避するために他の成果物が依存して、同じアプリケーションの依存関係を持つすべての成果物をまとめておくために利用できます。 これは常に可能であれば、ただし、ほとんどの種類のアイテムを BizTalk グループ内で一意でなければならないためです。 同じグループ内の 2 つの異なるアプリケーションに、同一アイテムに依存するアイテムが含まれていても、その同一アイテムを両方のアプリケーション内に含めることはできません。 一意の成果物の問題に関する詳細については、次を参照してください。[成果物をする必要がありますする内で一意で、アプリケーションまたはグループ](http://go.microsoft.com/fwlink/?LinkId=155141)(<http://go.microsoft.com/fwlink/?LinkId=155141>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
   1 つのアプリケーションに必要なアイテムを追加し、それに依存するアイテムを含むその他のアプリケーションからそのアプリケーションへの参照を追加できます。 アプリケーションへの参照を追加すると、アプリケーション内のアイテムで、参照先アプリケーション内の任意のアイテムを使用できるようになります。 参照を追加する方法の詳細については、次を参照してください。[別のアプリケーションへの参照を追加する方法](http://go.microsoft.com/fwlink/?LinkID=155011)(<http://go.microsoft.com/fwlink/?LinkID=155011>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
   BizTalk アプリケーション内のアイテムを更新するためのタスクのチェックリストについては、次を参照してください。[チェックリスト: BizTalk アプリケーション内のアイテムの更新](http://go.microsoft.com/fwlink/?LinkId=155647)(<http://go.microsoft.com/fwlink/?LinkId=155647>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
## <a name="see-also"></a>参照  
 [アプリケーションとアイテムの更新](../technical-guides/updating-applications-and-artifacts.md)