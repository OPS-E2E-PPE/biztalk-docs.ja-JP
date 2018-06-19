---
title: 使用する Web サービスの URI を変更する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, modifying
- Web services, consuming
- consuming [Web services]
- modifying, Web services
ms.assetid: 907de565-8c99-4d34-939f-fd3dba37dd11
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b9ae7d7178fc24c5f16b28325fb627045e5273a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247402"
---
# <a name="how-to-change-the-uri-of-a-consumed-web-service"></a>使用する Web サービスの URI の変更方法
オーケストレーションを展開すると、オーケストレーションが参照する各 Web サービスの送信ポートが BizTalk Server によって構成されます。 既定では、実行時の Web サービスの URL が、インポートされた Web サービスの URL にも使用されます。 この URL は、BizTalk Server 管理コンソールを使用して変更できます。  
  
> [!NOTE]
>  オーケストレーションは、使用する Web サービスの URI を変更する前に展開する必要があります。 オーケストレーションの展開の詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)です。  
  
### <a name="to-change-the-uri-of-a-consumed-web-service-using-biztalk-server-administration-console"></a>使用する Web サービスの URI を BizTalk Server 管理コンソールで変更するには  
  
1.  BizTalk Server 管理コンソールで、BizTalk アプリケーションを展開し、展開、**送信ポート**ノード。  
  
2.  SOAP アダプターで構成された送信ポートを右クリックし、をクリックして**プロパティ**です。  
  
3.  物理ポートがあるない場合は、送信ポートを作成し、BizTalk 管理コンソールを使用して受信場所。 詳細については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。  
  
4.  **送信プロパティ**ダイアログ ボックスで、をクリックして**構成**です。  
  
5.  **SOAP トランスポートのプロパティ** ダイアログ ボックスで、 **Web サービス URL**ボックス、Web サービスの場所の完全な URL を入力し、をクリックして**OK**です。  
  
    > [!NOTE]
    >  指定した URL に対応する Web サービスが存在することを確認してください。 BizTalk Server では URL の場所は検証されません。  
  
6.  終了するには、ok をクリックして、**送信プロパティ** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 管理コンソールを使用します。](../core/using-the-biztalk-server-administration-console.md)   
 [SOAP 送信ポートを構成する方法](../core/how-to-configure-a-soap-send-port.md)   
 [使用する Web サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-web-services.md)   
 [Web ポートの作成](../core/creating-web-ports.md)