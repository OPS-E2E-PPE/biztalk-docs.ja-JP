---
title: アダプター インターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7398aeb-7c1c-400e-a552-d0ab39e55a0b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717adcf5d4a706a7cc072b42b224ab0f9f8cc6fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225490"
---
# <a name="adapter-interfaces"></a>アダプター インターフェイス
カスタム アダプターには、実装する必要のあるインターフェイスが 3 つあります。また、省略可能なインターフェイスも 2 つあります。  
  
## <a name="mandatory-interfaces"></a>必須のインターフェイス  
 アダプターはすべて、次のインターフェイスを実装する必要があります。  
  
### <a name="ibasecomponent"></a>IBaseComponent  
 このインターフェイスの詳細、**名前**、**バージョン**、および**説明**アダプターのです。  
  
### <a name="ibttransport"></a>IBTTransport  
 このインターフェイスの詳細、**トランスポートの種類**と**ClassID**アダプターのです。  
  
### <a name="ibtbatchcallback"></a>IBTBatchCallback  
 このインターフェイスは、アダプターが、メッセージング エンジンに送信されるメッセージのバッチの状態やエラー情報を受信するコールバック インターフェイスです。  
  
## <a name="optional-interfaces"></a>省略可能なインターフェイス  
 次のインターフェイスは、必要に応じてアダプターに実装します。  
  
### <a name="ipersistpropertybag"></a>IPersistPropertyBag  
 これは、ハンドラー構成がアダプターに送信されるときに使用される構成インターフェイスです。 このインターフェイスは、ハンドラー構成情報を持っているアダプターの場合にのみ必要です。  
  
### <a name="ibttransportcontrol"></a>IBTTransportControl  
 このインターフェイスはアダプターを初期化および終了するために使用します。 アダプターのトランスポート プロキシはこのインターフェイスを通じて渡されます。 このインターフェイスは、分離アダプターの場合は不要です。