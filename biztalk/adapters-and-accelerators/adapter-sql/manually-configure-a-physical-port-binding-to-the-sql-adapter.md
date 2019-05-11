---
title: SQL アダプターを物理ポートのバインドを手動で構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d3f0bb78-c85f-4629-9e2d-cce180ff78ae
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fccfcfed0e965831d0c40ccde94348440db357e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368788"
---
# <a name="manually-configure-a-physical-port-binding-to-the-sql-adapter"></a>SQL アダプターを物理ポートのバインドを手動で構成します。
このセクションでは、構成に関する情報を提供、 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] WCF カスタム バインドとして、またはを使用して WCF SQL ポートとして、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 アダプタの展開後にすることを使用しての SQL Server からメッセージを送受信、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 アダプターを展開する手順は、に応じて異なります。  
  
- 間の通信の方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 受信、送信を構成することができます、または送信の受信ポート。 選択内容は、次の表にまとめたものです。  
  
  |ポートの方向|通信方式|選択する通信の方向|  
  |--------------------|---------------------------|-----------------------------------------------|  
  |Send|一方向|常にこのポートでメッセージを送信します。|  
  |Receive|一方向|常にこのポートでメッセージを受信します。|  
  |送受信|要求 - 応答|要求の送信と応答の受信をされます。|  
  
  > [!NOTE]
  >  双方向受信ポートでサポートされていない、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
   詳細については、次を参照してください。[送信ポートを作成する方法](../../core/how-to-create-a-send-port2.md)、または[受信ポートを作成する方法](../../core/how-to-create-a-receive-port.md)します。 
  
- かどうか、アダプターでは、SQL Server (送信操作) にメッセージを送信または、(受信操作) の SQL Server からメッセージを受信します。 によって送信またはメッセージを受信するかどうかを作成、送信または受信ポート、それぞれします。  
  
  > [!NOTE]
  >  構成、送信またはによって作成されるバインド構成ファイルをインポートしてポートを受信することができますも、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部として。 このバインド ファイルを使用してポートを構成する方法の詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)します。
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Wcf-custom アダプタと SQL アダプタを使用してポートを構成します。](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)  
  
-   [WCF-SQL アダプターを使用してポートを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-sql-adapter.md)  
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)