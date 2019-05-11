---
title: 使用する Web サービスの URI を変更する方法 |Microsoft Docs
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
ms.openlocfilehash: c5fd101ba0553397b6c7144545a9ac557ceada03
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342390"
---
# <a name="how-to-change-the-uri-of-a-consumed-web-service"></a>使用する Web サービスの URI の変更方法
オーケストレーションを展開した後、BizTalk Server は、オーケストレーションが参照される各 Web サービス用の送信ポートを構成します。 既定では、BizTalk は、実行時にインポートされた Web サービスに対する同じ URL の Web サービスの URL を使用します。 BizTalk Server 管理コンソールを使用して、この URL を変更することができます。  
  
> [!NOTE]
>  使用する Web サービスの URI を変更する前に、オーケストレーションを展開する必要があります。 オーケストレーションの展開の詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)します。  
  
### <a name="to-change-the-uri-of-a-consumed-web-service-using-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールを使用して使用する Web サービスの URI を変更するには  
  
1.  BizTalk Server 管理コンソールで、BizTalk アプリケーションを展開し、展開、**送信ポート**ノード。  
  
2.  SOAP アダプターで構成された送信ポートを右クリックし、をクリックして**プロパティ**します。  
  
3.  物理ポートがいない場合は、送信ポートを作成し、BizTalk 管理コンソールを使用して受信場所。 詳しくは、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)します。  
  
4.  **送信プロパティ**ダイアログ ボックスで、をクリックして**構成**します。  
  
5.  **SOAP トランスポートのプロパティ** ダイアログ ボックスで、 **Web サービスの URL**ボックスに、Web サービスの場所の完全な URL を入力し、 をクリックして**OK**。  
  
    > [!NOTE]
    >  指定された URL の Web サービスが存在することを確認してください。 BizTalk Server では、URL の場所は検証されません。  
  
6.  終了するには、ok をクリックして、**送信プロパティ** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 管理コンソールの使用](../core/using-the-biztalk-server-administration-console.md)   
 [SOAP 送信ポートを構成する方法](../core/how-to-configure-a-soap-send-port.md)   
 [消費済み Web サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-web-services.md)   
 [Web ポートの作成](../core/creating-web-ports.md)