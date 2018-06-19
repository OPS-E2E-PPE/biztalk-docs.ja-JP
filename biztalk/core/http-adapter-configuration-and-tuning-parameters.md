---
title: HTTP アダプタの構成およびチューニング パラメータ |Microsoft ドキュメント
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
ms.openlocfilehash: 5db4f4dc4403ddfbf677ac2729c00e2b1976db61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257786"
---
# <a name="http-adapter-configuration-and-tuning-parameters"></a>HTTP アダプタの構成およびチューニング パラメータ
HTTP アダプタの構成およびチューニング パラメータの一部には、レジストリ キー エントリから、また BizTalk Server インストールのルート ディレクトリにある BTSNTSvc.exe.config 構成ファイルを変更することによってアクセスできます。  
  
 **HTTP アダプタのパフォーマンスに影響するレジストリ設定**  
  
 次の表は、HTTP アダプタのパフォーマンスに影響するレジストリ設定を示しています。 既定ではレジストリに HTTP アダプタのキーがないため、HTTP アダプタでは既定の設定が使用されることに注意してください。 既定の設定を変更する必要がある場合は、次に示すようにレジストリ内の場所にレジストリ キーを作成する必要があります。  
  
-   **DisableChunkEncoding**、 **RequestQueueSize**、および**HttpReceiveThreadsPerCpu**で定義する必要があります**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\HttpReceive**です。  
  
-   **HttpOutTimeoutInterval**、 **HttpOutInflightSize**、および**HttpOutCompleteSize**で定義する必要があります**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc {GUID}** 場所**GUID** HTTP 送信ハンドラのホストの id を指定します。  
  
|キー名|型|既定値|説明|  
|--------------|----------|-------------|-----------------|  
|**DisableChunkEncoding**|DWORD|0|クライアントに応答を返すときに、HTTP 受信アダプタでチャンク エンコードを使用するかどうかを規制します。<br /><br /> HTTP 受信アダプタの応答にチャンク エンコードを使用しない場合、0 以外の値に設定します。<br /><br /> **最小値:** 0<br /><br /> **最大値:** 0 以外の値|  
|**RequestQueueSize**|DWORD|256|HTTP 受信アダプタで一度に処理される同時実行要求の数を定義します。<br /><br /> **最小値:** 10<br /><br /> **最大値:** 2048|  
|**HttpReceiveThreadsPerCpu**|DWORD|2|HTTP 受信アダプタに割り当てられている CPU ごとのスレッドの数を定義します。<br /><br /> **最小値:** 1<br /><br /> **最大値:** 10|  
|**HttpOutTimeoutInterval**|DWORD|2000|タイムアウトする前に、HTTP 送信アダプタが待機する間隔を秒単位で定義します。<br /><br /> **最小値:** 500<br /><br /> **最大値:** 10000000|  
|**HttpOutInflightSize**|DWORD|100|BizTalk Server の HTTP 送信アダプタのインスタンスによって処理される、同時実行 HTTP 要求の最大数です。<br /><br /> 待機時間の推奨値は 3 ~ 5 倍の間、 **maxconnection**構成ファイル エントリを次に説明します。<br /><br /> **最小値:** 1<br /><br /> **最大値:** 1024|  
|**HttpOutCompleteSize**|DWORD|5|HTTP 送信アダプターから返されるバッチ メッセージのサイズを制御します。 バッファーがいっぱいでないと、未処理の応答がある場合、アダプターはバッチをコミットするまで 1 秒間待機します。  低待機時間シナリオでは、これは処理のメッセージ ボックスにすぐに応答メッセージを送信するアダプターを 1 に設定する必要があります。<br /><br /> **最小値:** 1<br /><br /> **最大値:** 1024|  
  
 **特定の接続先サーバーに、HTTP 送信アダプターによって行われた同時接続数を制御するために構成ファイル エントリ**  
  
 BizTalk Server インストールのルート ディレクトリにある BTSNTSvc.exe.config ファイルにエントリを作成することで、HTTP アダプタから特定の接続先サーバーに開かれる同時接続の数を構成できます。  
  
> [!NOTE]
>  このプロパティは、HTTP アダプタと SOAP アダプタから同じ HTTP サーバーにメッセージを送信する場合に、両方のアダプタに適用されます。 "Maxconnnection"プロパティの既定値は 2、すべての Uri の"maxconnection"プロパティを設定できる最大値は 20 です。  
  
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
 [HTTP アダプタの構成](../core/configuring-the-http-adapter.md)