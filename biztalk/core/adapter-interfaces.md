---
title: アダプター インターフェイス |Microsoft Docs
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
ms.openlocfilehash: 4bdb6f3e26d8862fd538f0279ecbb4c5c9b33af8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361404"
---
# <a name="adapter-interfaces"></a>アダプター インターフェイス
カスタム アダプターを実装する必要があります、3 つのインターフェイスと省略可能な 2 つのインターフェイスがあります。  
  
## <a name="mandatory-interfaces"></a>必須のインターフェイス  
 すべてのアダプターでは、次のインターフェイスを実装する必要があります。  
  
### <a name="ibasecomponent"></a>IBaseComponent  
 このインターフェイスの詳細、**名前**、**バージョン**、および**説明**アダプターの。  
  
### <a name="ibttransport"></a>IBTTransport  
 このインターフェイスの詳細、**トランスポートの種類**と**ClassID**のアダプター。  
  
### <a name="ibtbatchcallback"></a>IBTBatchCallback  
 このインターフェイスは、アダプター情報を受信状態やエラー メッセージのバッチのメッセージング エンジンに送信されるコールバック インターフェイス。  
  
## <a name="optional-interfaces"></a>省略可能なインターフェイス  
 アダプターは、必要に応じて、次のインターフェイスを実装していません。  
  
### <a name="ipersistpropertybag"></a>IPersistPropertyBag  
 これは、どのハンドラーを通じて構成は、アダプターに配信構成インターフェイスです。 このインターフェイスは、ハンドラーの構成情報を持つアダプターに対してのみ必要です。  
  
### <a name="ibttransportcontrol"></a>IBTTransportControl  
 このインターフェイスは初期化し、アダプターの終了に使用されます。 アダプターのトランスポート プロキシは、このインターフェイスを使用して渡されます。 このインターフェイスは、分離アダプターの必要はありません。