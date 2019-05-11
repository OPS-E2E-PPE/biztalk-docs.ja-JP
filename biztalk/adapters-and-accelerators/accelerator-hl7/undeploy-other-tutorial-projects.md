---
title: その他のチュートリアルのプロジェクトを展開解除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fce837f-1853-4d5d-a680-8ae2a974c750
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4de399020c4fe41f3c65d3e6119cbe11469efd5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286387"
---
# <a name="undeploy-other-tutorial-projects"></a>その他のチュートリアルのプロジェクトを展開解除します。
BizTalk Accelerator for HL7 に展開するときに ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) チュートリアルでは、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]チュートリアルのアセンブリ ファイルの構成データベース (BizTalk 管理データベースとも呼ばれます) とグローバル アセンブリ キャッシュに格納します。 別に実行している場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]チュートリアル、およびデプロイされたそのチュートリアルで作成したアセンブリ、バッチ処理のチュートリアルの 3 つの部分で、アセンブリをテストするときにエラーを発生可能性があります。 これは、1 つのメッセージ スキーマを一度に 1 つのみ展開できるために発生する可能性があります。  
  
 前のチュートリアルに展開されたアセンブリを展開解除によってこれらのエラーを回避できます。 必要な場合は、後で、アセンブリを再展開することができます。  
  
 アセンブリの展開を解除する前に、アセンブリ内のオーケストレーションを参加解除する必要があります。 また、デプロイを保持する他のアセンブリから展開を解除するアセンブリへの参照を削除する必要があります。 別の方法では、別のチュートリアルを開始する前に、1 つのチュートリアルに関連付けられているすべての Dll を削除します。  
  
### <a name="to-undeploy-an-assembly"></a>アセンブリを展開解除するには  
  
1. Visual Studio の BizTalk エクスプ ローラーでオーケストレーションをクリックし、をクリックして展開解除するアセンブリで使用するオーケストレーションを参加解除**参加解除**します。  
  
2. デプロイを保持する任意のアセンブリでは、展開を解除するアセンブリへの参照を削除します。 ソリューション エクスプ ローラーで参照を右クリックし、をクリックし、**削除**します。  
  
3. BizTalk エクスプ ローラーを開き、クリックしての展開を解除するアセンブリを右クリックして**Undeploy**します。  
  
   アセンブリの展開解除の詳細については、「展開を解除するアセンブリを使用して BizTalk エクスプ ローラー」を BizTalk Server ヘルプを参照してください。  
  
## <a name="see-also"></a>参照  
 [バッチ処理のチュートリアルを使用するための準備](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)