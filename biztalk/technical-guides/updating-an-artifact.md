---
title: 成果物の更新 |Microsoft ドキュメント
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
ms.openlocfilehash: 17d5f2ad910c59ded9c2499c929d73480fac7b51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302578"
---
# <a name="updating-an-artifact"></a>成果物の更新
2 つ以上の BizTalk アプリケーション内のアイテム間の依存関係には、アプリケーションの展開と保守に大きな影響を及ぼすことができます。 その成果物を正常に機能するために使用する必要があるときに、成果物は別に依存して、たとえば、オーケストレーションが必要なメッセージを正しく送信するために特定のパイプラインを使用します。  
  
 アプリケーション内の成果物を更新するには、必要があります最初を展開解除する、それに依存するすべてのアイテムと共にします。 依存関係にあるアイテムが同じアプリケーション内に存在する場合、更新されるアイテムと依存するアイテムの展開解除タスクと再展開タスクが、BizTalk Server によって自動的に実行されます。 しかし、依存関係にあるアイテムが別のアプリケーションに存在する場合は、動作が異なります。 1 つのアプリケーション内のアイテムを更新するし、それに依存している別のアプリケーション内の成果物を展開解除して、依存するアイテムを次のように手動で再展開する必要があります。  
  
1.  依存するアイテムの停止、参加解除、およびバインド解除を行います。  
  
2.  依存先のアイテムを更新します。  
  
3.  依存するアイテムをバインドし、参加させ、開始します。  
  
 手動でアイテムを更新する手順を実行する必要を避けるために他のアイテムが依存して、同じアプリケーションの依存関係を持つすべてのアイテムをまとめておくためしようとすることができます。 これは常に可能であれば、ただし、ほとんどの成果物の種類は、BizTalk グループ内で一意である必要があります。 同じグループ内の 2 つの異なるアプリケーションに、同一アイテムに依存するアイテムが含まれていても、その同一アイテムを両方のアプリケーション内に含めることはできません。 一意の成果物の問題に関する詳細については、次を参照してください。[成果物をする必要がありますする内で一意のアプリケーションまたはグループ](http://go.microsoft.com/fwlink/?LinkId=155141)(http://go.microsoft.com/fwlink/?LinkId=155141) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
 1 つのアプリケーションに必要なアイテムを追加し、それに依存するアイテムを含むその他のアプリケーションからそのアプリケーションへの参照を追加できます。 アプリケーションへの参照を追加すると、アプリケーション内のアイテムで、参照先アプリケーション内の任意のアイテムを使用できるようになります。 参照を追加する方法の詳細については、次を参照してください。[を別のアプリケーションへの参照を追加する方法](http://go.microsoft.com/fwlink/?LinkID=155011)(http://go.microsoft.com/fwlink/?LinkID=155011) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
 BizTalk アプリケーション内のアイテムを更新するためのタスクのチェックリストについては、次を参照してください。[チェックリスト: BizTalk アプリケーション内のアイテムの更新](http://go.microsoft.com/fwlink/?LinkId=155647)(http://go.microsoft.com/fwlink/?LinkId=155647) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
## <a name="see-also"></a>参照  
 [アプリケーションとアイテムの更新](../technical-guides/updating-applications-and-artifacts.md)