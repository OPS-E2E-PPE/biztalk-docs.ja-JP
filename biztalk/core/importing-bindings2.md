---
title: インポート Bindings2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, requirements
- importing, bindings
- bindings, importing
ms.assetid: 9e10bc04-aba8-430a-b8fd-de9399d54f88
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fab3b7677336a2d10daf365d7bf58d3c90aa9f35
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382528"
---
# <a name="importing-bindings"></a>バインドのインポート
このセクションの各トピックでは、バインドを BizTalk グループまたはアプリケーションにインポートする方法について説明します。  

 バインドをインポートする際は、次の点に注意してください。  

- **既存のバインドは上書きされます。** インポートするバインドの名前が既存のバインドと同じ場合、既存のバインドは上書きされます。 また、バインド ファイルにパーティとエイリアスが含まれている場合、アプリケーション内にある同じ名前のパーティとエイリアスのバインドは上書きされます。  

- **グループのすべてのバインドは、一意である必要があります。** インポートするバインドと同じ名前のバインドがグループに存在する場合、インポート操作に失敗します。  

- **パスワードを再構成する必要があります。** セキュリティ上の理由により、BizTalk Server では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。 バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。 BizTalk Server 管理コンソールの [トランスポートのプロパティ] ダイアログ ボックスで、送信ポートと受信場所のパスワードをそれぞれ構成します。 手順については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)します。 参照してください[を作成する方法、受信場所](../core/how-to-create-a-receive-location.md)します。  

- **ホストは、グループ内に存在する必要があります。** バインドで指定されているホストに対応するホストは、バインドのインポート先の BizTalk グループ内に存在し、ホストの信頼レベルが一致する必要があります。 そうでない場合、インポート操作が失敗します。  

- **バインドのインポートの動作は、バインドのソースによって異なります。** バインドのエクスポート元としては、アセンブリ、アプリケーション、グループが考えられます。 次の表に示すように、インポート操作の結果は、バインドがどこからエクスポートされたかによって異なります。  


  |        バインドのエクスポート元         |                                                                        アプリケーションへのインポート                                                                        |                                                                                                     グループへのインポート                                                                                                      |
  |---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  |  アセンブリからエクスポートされたバインド   | 指定されたアプリケーションには、バインド ファイルのエクスポート元アセンブリと同じ名前のアセンブリが含まれている必要があります。 それ以外の場合、インポート操作が失敗します。 |                        グループには、バインド ファイルのエクスポート元のアセンブリおよびアプリケーションと同じ名前のアセンブリおよびアプリケーションが含まれている必要があります。 それ以外の場合、インポートは失敗します。                        |
  | アプリケーションからエクスポートされたバインド |            バインド ファイルのエクスポート元アプリケーションは、指定されたアプリケーションと同じ名前であることが必要です。 それ以外の場合、インポート操作が失敗します。            |                バインド ファイルのエクスポート元アプリケーションは、バインドをインポートするグループのアプリケーションと同じ名前であることが必要です。 それ以外の場合、インポート操作が失敗します。                |
  |    グループからエクスポートされたバインド     | バインド ファイルのエクスポート元グループには、指定されたアプリケーションと同じ名前のアプリケーションが存在していることが必要です。 それ以外の場合、インポート操作が失敗します。  | バインドのインポートは、対応するアプリケーション間で行われます。 つまり、エクスポート元グループにおけるアプリケーションのバインドは、現在のグループで同じ名前を持つアプリケーションにインポートされます。 |


- **アダプターの Name 属性が正しくない可能性があります。** バインド ファイルにアダプターの設定が含まれている場合は、バインド ファイル内に指定されている TransportType 要素の Name 属性の値が、BizTalk Server 管理コンソールでアダプターに設定されている名前と同じであることを確認してください ([プラットフォームの設定]、[アダプター] の順にクリックします)。  

   バインドをインポートするときに、ケースあることを確認する必要があります具体的には、 [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] BizTalk Server にします。 名前が異なると問題が発生する可能性があります。  

  -   MQS  

  -   MSMQ (MSMQ)  

  -   POP3  

  -   Windows SharePoint Services  

## <a name="in-this-section"></a>このセクションの内容  

-   [BizTalk グループにバインドをインポートする方法](../core/how-to-import-bindings-into-a-biztalk-group.md)  

-   [BizTalk アプリケーションにバインドをインポートする方法](../core/how-to-import-bindings-into-a-biztalk-application.md)  

-   [Edi-as2 ソリューションのバインドをインポートする方法](../core/how-to-import-bindings-for-an-edi-as2-solution.md)