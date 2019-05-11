---
title: FileAct アダプター ファイルおよび転送 Id |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a9aaff1-8816-42cf-b100-fedf964caaf5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4530a524518c96db0b42cbae456ba6705e2e9b0c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367197"
---
# <a name="fileact-adapter-file-and-transfer-identification"></a>FileAct アダプター ファイルおよび転送 Id
A4SWIFT FileAct アダプターでは、実行時にファイルおよび転送の識別の詳細を指定する、開発者が許可されます。 これらのパラメーターを以下に示します。  
  
-   **物理ファイル名**– 読み取りまたは書き込みするファイルの名前と完全なパス。 このパラメーターが渡されないとは、ファイル ハンドラー コンポーネントに対してローカルです。  
  
-   **論理ファイル名**– SWIFTNet 間で、受信アプリケーションへの送信元アプリケーションからファイル名が渡されます。 これは省略可能でと、指定しない場合、パスを使用せずに物理ファイル名が使用します。  
  
-   **ファイル転送イベント エンドポイント**– プリミティブのイベントのサブスクライブでファイル転送イベントを処理するアプリケーションで指定された名前。 このパラメーターは、イベントのレポートを受信するアプリケーションにファイル転送をリンクします。  
  
-   **ファイル転送参照**– トークン文字列が作成され、それ自体、転送のハンドルとして FileAct サブシステムで使用します。 FileAct アダプターのに関する限り、この移行に固有の文字列だけです。  
  
-   **キーを転送**– の転送を識別するためにアプリケーションによって割り当てられた文字列は、目的を中止します。 アプリケーションで指定されていない場合、ファイルに関連付けられた GUID になります。  
  
-   **パーティションを転送**– 複数の転送を関連付けに使用する文字列。 指定しない場合、呼び出しで開発者が、これを"Application Name"、関連する送信の定義時に指定するまたは受信場所します。  
  
-   **ユーザー参照**– 非否認の転送を一意に識別するアプリケーションで定義されている文字列。 アプリケーションで指定されていない場合、ファイルに関連付けられた GUID になります。  
  
-   **メッセージ ID** – 最初の要求または応答を一意に定義する識別子。 これは、送信アダプターによって生成されると、適切な要求または応答メッセージに関連付けられた GUID です。 したがって、クライアントは要求のメッセージ ID を生成し、サーバーは応答の。  
  
## <a name="see-also"></a>参照  
 [FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct アダプターのリアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct アダプターのストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct アダプターのサポート情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct アダプターの配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct アダプターの状態監視](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)