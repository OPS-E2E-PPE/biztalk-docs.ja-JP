---
title: SAP アダプターのサンプル |Microsoft Docs
description: SAP 向け BizTalk Server、WCF サービス モデル、WCF チャネル モデル、およびデータ プロバイダーで使用できる mySAP WCF アダプタのサンプル
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4654c458-83be-417f-ae54-5c3a8f6ab81f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 272f07f637f276f1d56767eaab78b97d9e343667
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373074"
---
# <a name="samples-for-the-sap-adapter"></a>SAP アダプターのサンプル
サンプルは[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]に分類されます。  

- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] サンプル  

- WCF サービス モデルのサンプル  

- WCF チャネル モデルのサンプル  

- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] サンプル  


 サンプルについては、「 [BizTalk Adapter Pack 2010。SAP アダプタ サンプル](https://www.microsoft.com/download/details.aspx?id=1314)します。 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]

 サンプルを次に示します。

## <a name="biztalk-server-samples"></a>BizTalk Server のサンプル  

|サンプルのディレクトリ名|説明|  
|---------------------------|-----------------|  
|IDOCSend|IDOC を SAP システムに送信する方法を示します。|  
|ReceiveIDOC|SAP システムから IDOC を受信する方法を示します。|  
|ReceiveIDOC_SYSREL|SAP システムから IDOC を受信する方法を示します。 IDOC を受信中は、SAP SYSREL より小さい、バージョン番号です。|  
|RFCServer|SAP システムから RFC サーバー呼び出しを受信する方法を示します。|  
|SAPTransaction|使用して SAP システムでトランザクションを実行する方法を示します。|  
|tRFCClient|SAP システム上 tRFC クライアント呼び出しを行う方法を示します。|  

## <a name="wcf-service-model-samples"></a>WCF サービス モデルのサンプル   

|サンプルのディレクトリ名|説明|  
|---------------------------|-----------------|  
|SapIdocStringClientSM|SendIdoc 操作を呼び出すことによって、SAP システムに IDOC を送信する方法を示します。|  
|SapRfcServerSM|SAP システムから RFC サーバー呼び出しを受信する方法を示します。|  
|SapBapiTxClientSM|SAP システムでのトランザクション内での Bapi を呼び出す方法を示します。|  
|SapTrfcClientSM|SAP システムで tRFC クライアント呼び出しを起動する方法を示します。|  

## <a name="wcf-channel-model-samples"></a>WCF チャネル モデルのサンプル  

|サンプルのディレクトリ名|説明|  
|---------------------------|-----------------|  
|SapIdocReceiveCM|SAP システムから Idoc を受信する方法を示します|  
|SapRfcServerCM|SAP システムから RFC サーバー呼び出しを受信する方法を示します。|  

## <a name="data-provider-for-sap-samples"></a>SAP のサンプルのデータ プロバイダー  

| サンプルのディレクトリ名 |                                             説明                                              |
|-----------------------|------------------------------------------------------------------------------------------------------|
|        sap の ado        | 使用する方法を示します、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]します。 |

## <a name="see-also"></a>参照  
[SAP アプリケーションを開発する](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)