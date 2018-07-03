---
title: 例外とエラーの Siebel アダプターの処理 |Microsoft Docs
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
ms.openlocfilehash: 67a615bec1bf1b8cd29e84728f39d6fea626f16e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977122"
---
# <a name="exceptions-and-error-handling-with-the-siebel-adapter"></a>例外とエラーの Siebel アダプターの処理
## <a name="exception-list"></a>例外の一覧
によってスローされた例外、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]します。 これらを含めることができます。  
  
- 内部例外、.NET Framework をスローする、システム例外  
  
- LOB クライアント ライブラリをスローする LOB 例外。  
  
  詳細については、内部例外は、それぞれの .NET Framework または Siebel のドキュメントを参照してください。 例外には、問題の解決に役立つ詳細なエラー メッセージも含まれています。 ここで説明する例外の一覧は包括的なしないことに注意してください。  
  
|例外|考えられる原因/エラーの説明|  
|---------------|---------------------------------------|  
|ConnectionException|アダプターは、Siebel システムへの既存の接続を閉じたりする接続を確立できない場合、この例外をスローします。|  
|CredentialsException|アダプターは、アダプターのクライアントが、ユーザー名または Siebel システムに接続するためのパスワードを指定しない場合、この例外をスローします。|  
|MetadataException|アダプターは、Siebel の成果物のメタデータの取得に失敗した場合、この例外をスローします。|  
|XmlReaderParsingException|アダプターは、操作を呼び出す、Siebel システムでアダプター クライアントによって提供される入力情報が不完全であるか、または正しくない場合、この例外をスローします。|  
|XmlReaderGenerationException|アダプターは、Siebel システムで実行される操作の出力を生成できない場合、この例外をスローします。|  
|TargetSystemException|場合、アダプターはこの例外をスローします。 アダプターはを使用して、Siebel COM API で Siebel システム、例外をスローします。 内部例外には、Siebel の COM API によってスローされる例外が含まれています。|  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Siebel eBusiness Applications についてください。](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)   
[Siebel アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)