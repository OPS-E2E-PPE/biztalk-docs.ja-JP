---
title: "SQL アダプターを物理ポートのバインドを手動で構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3f0bb78-c85f-4629-9e2d-cce180ff78ae
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac72d914539eabc9b129985c2b9335270e561d18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="manually-configure-a-physical-port-binding-to-the-sql-adapter"></a>SQL アダプターを物理ポートのバインドを手動で構成します。
このセクションの構成に関する情報を提供する、 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] WCF カスタム バインドとして、またはを使用して WCF SQL ポートとして、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 アダプターを展開したらことができますを使用しての SQL Server からメッセージを送受信する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 アダプタの展開の手順が異なります。  
  
-   間の通信の方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 [受信] の送信を構成することもできますまたは送受信ポートです。 選択した内容は、次の表にまとめたものです。  
  
    |ポートの方向|通信方式|選択への通信方向|  
    |--------------------|---------------------------|-----------------------------------------------|  
    |Send|一方向|常にこのポートでメッセージを送信します。|  
    |Receive|一方向|常にこのポートでメッセージを受信します。|  
    |送受信|要求 - 応答|要求の送信と応答の受信をされます。|  
  
    > [!NOTE]
    >  双方向受信ポートでサポートされていない、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
     詳細については、次を参照してください。[送信ポートを作成する方法](../../core/how-to-create-a-send-port2.md)、または[受信ポートを作成する方法](../../core/how-to-create-a-receive-port.md)です。 
  
-   かどうか、アダプターは、SQL Server (送信操作) にメッセージを送信または SQL Server (入力方向の操作) からメッセージを受信します。 送信またはメッセージを受信するかどうかは、によってを作成、送信または受信ポートをそれぞれします。  
  
    > [!NOTE]
    >  また、送信構成またはによって作成されるバインディングの構成ファイルをインポートしてポートを受信する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部として。 このバインド ファイルを使用するポートを構成する方法の詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Wcf-custom アダプタと SQL アダプタを使用してポートを構成します。](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)  
  
-   [WCF-SQL アダプターを使用してポートを構成します。](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-sql-adapter.md)  
  
## <a name="see-also"></a>参照  
[SQL アダプタを BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)