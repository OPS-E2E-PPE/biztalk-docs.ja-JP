---
title: 例外とエラーの Siebel アダプターの処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error handling, troubleshooting
- exceptions, troubleshooting
- troubleshooting, exceptions and error handling
ms.assetid: d46e908f-0715-43e2-879b-f5d0beb9bc64
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 743e2a0f03e35282c24a506ff37e9d774f0b7505
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221866"
---
# <a name="exceptions-and-error-handling-with-the-siebel-adapter"></a>例外とエラーの Siebel アダプターの処理
## <a name="exception-list"></a>例外の一覧
によってスローされた例外、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]です。 これらを含めることができます。  
  
-   システム例外、.NET Framework をスローするは、内部例外  
  
-   LOB LOB クライアント ライブラリからスローされる例外。  
  
 詳細については、内部例外は、それぞれの .NET Framework または Siebel のドキュメントを参照してください。 例外には、問題の解決に役立つ詳細なエラー メッセージも含まれています。 ここで説明した例外のリストが包括的ながないことに注意してください。  
  
|例外|考えられる原因/エラーの説明|  
|---------------|---------------------------------------|  
|使用して ConnectionException|アダプターは、Siebel システムへの既存の接続を閉じたり、接続を確立することがない場合、この例外をスローします。|  
|CredentialsException|アダプターは、ユーザー名またはパスワード、Siebel システムへの接続にアダプタのクライアントが指定されていない場合、この例外をスローします。|  
|MetadataException|アダプターは、Siebel の成果物のためのメタデータの取得に失敗した場合は、この例外をスローします。|  
|XmlReaderParsingException|アダプターは、Siebel システムでは操作を呼び出すをクライアント側アダプターによって提供される入力情報が不完全か、または正しくない場合、この例外をスローします。|  
|XmlReaderGenerationException|アダプターは、Siebel システムで実行される操作の出力を生成することがない場合、この例外をスローします。|  
|TargetSystemException|場合、アダプターがこの例外をスローするアダプターを使用して、Siebel COM API で、例外をスロー、Siebel システムとのインターフェイスです。 内部例外には、Siebel COM API によってスローされる例外が含まれています。|  
  
## <a name="see-also"></a>参照  
 [Siebel eBusiness Applications の BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)   
[Siebel アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)