---
title: HTTP アダプターの構成およびチューニング パラメータ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, parameters
- configuring [HTTP adapters], parameters
- HTTP adapters, tuning
- RequestQueueSize key [HTTP adapters]
- HttpReceiveThreadsPerCpu key [HTTP adapters]
- HttpOutTimeoutInterval key [HTTP adapters]
- HttpOutInflightSize key [HTTP adapters]
- configuring [HTTP adapters], tuning
- DisableChunkEncoding key [HTTP adapters]
- HttpOutCompleteSize key [HTTP adapters]
ms.assetid: c8989a88-722a-40b5-94cf-4b6840add02e
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaae6d5cf3a5f810a8c8340a07d1a94fab974afe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383029"
---
# <a name="http-adapter-configuration-and-tuning-parameters"></a>HTTP アダプターの構成およびチューニング パラメーター
いくつかの構成およびチューニング パラメータは、HTTP アダプタと BizTalk Server のインストール ディレクトリのルートにある BTSNTSvc.exe.config ファイルの変更を使用してレジストリ キー エントリにアクセスできます。  
  
 **HTTP アダプターのパフォーマンスに影響を与えるレジストリ設定**  
  
 次の表では、HTTP アダプタのパフォーマンスに影響するレジストリ設定について説明します。 既定でがない HTTP アダプタのキー レジストリでは、HTTP アダプター、既定の設定を使用するように注意してください。 を既定の設定を変更する必要がある場合は、レジストリで、次の場所では、次のレジストリ キーを作成する必要があります。  
  
-   **DisableChunkEncoding**、 **RequestQueueSize**、および**HttpReceiveThreadsPerCpu**で定義する必要があります**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\HttpReceive**します。  
  
-   **HttpOutTimeoutInterval**、 **HttpOutInflightSize**、および**HttpOutCompleteSize**で定義する必要があります**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc {GUID}** 場所**GUID** HTTP 送信ハンドラのホストの ID です。  
  
|キー名|型|既定|説明|  
|--------------|----------|-------------|-----------------|  
|**DisableChunkEncoding**|DWORD|0|規制アダプターが、クライアントへの応答を送信するときに、チャンク エンコードを使用して、HTTP 受信かどうか。<br /><br /> HTTP 受信アダプタの応答にチャンク エンコードをオフに 0 以外の値に設定します。<br /><br /> **最小値:** 0<br /><br /> **最大値:** 0 以外の値|  
|**RequestQueueSize**|DWORD|256|受信アダプターの処理を同時に、HTTP の同時要求の数を定義します。<br /><br /> **最小値:** 10<br /><br /> **最大値:** 2048|  
|**HttpReceiveThreadsPerCpu**|DWORD|2|定義受信アダプター、HTTP に割り当てられている CPU あたりのスレッドの数。<br /><br /> **最小値:** 1<br /><br /> **最大値:** 10|  
|**HttpOutTimeoutInterval**|DWORD|2000|HTTP 送信アダプターがタイムアウトになるまで待機する秒単位で間隔を定義します。<br /><br /> **最小値:** 500<br /><br /> **最大値:** 10000000|  
|**HttpOutInflightSize**|DWORD|100|これは、BizTalk Server の HTTP 送信アダプタのインスタンスを処理する同時実行の HTTP 要求の最大数です。<br /><br /> 待機時間の推奨値が 3 ~ 5 倍の間は、 **maxconnection**構成ファイルのエントリ以下で説明します。<br /><br /> **最小値:** 1<br /><br /> **最大値:** 1024|  
|**HttpOutCompleteSize**|DWORD|5|コントロールの HTTP から返されるメッセージのバッチ サイズは、アダプターを送信します。 バッファーがいっぱいでないと、未処理の応答がある場合、アダプターは、バッチがコミットされるまで 1 秒間待機します。  低待機時間シナリオは、これは処理のメッセージ ボックスにすぐに応答メッセージを送信するアダプターを 1 に設定する必要があります。<br /><br /> **最小値:** 1<br /><br /> **最大値:** 1024|  
  
 **特定の宛先サーバーに HTTP 送信アダプターによって行われる同時接続数を制御する構成ファイル エントリ**  
  
 HTTP アダプターが、特定の移行先サーバーに表示される同時接続数は、BizTalk Server のインストール ディレクトリのルートにある BTSNTSvc.exe.config ファイルにエントリを作成して構成できます。  
  
> [!NOTE]
>  このプロパティから同じ HTTP サーバーにメッセージを送信する場合、HTTP および SOAP の両方のアダプターに適用されます。 "Maxconnnection"プロパティの既定値は 2、すべての Uri の"maxconnection"プロパティを設定できる最大値は 20 です。  
  
 "最大接続数" プロパティの構成例を次に示します。  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "20" />  
      <add address = "http://www.northwind.com" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>参照  
 [HTTP アダプターの構成](../core/configuring-the-http-adapter.md)