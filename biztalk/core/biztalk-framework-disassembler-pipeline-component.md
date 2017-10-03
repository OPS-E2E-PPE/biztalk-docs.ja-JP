---
title: "BizTalk Framework 逆アセンブラー パイプライン コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Disassembler
- BizTalk Framework Disassembler [pipeline component]
ms.assetid: 48d6c530-5c02-4c70-ad11-0ea6c3c808f8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1ab54ddb9ef0b5fa389e6716fc4426978dcbd7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-framework-disassembler-pipeline-component"></a>BizTalk Framework 逆アセンブラー パイプライン コンポーネント
BizTalk Framework 逆アセンブラー パイプライン コンポーネントでは、XML データを解析して、そのデータに BizTalk Framework ベースのメッセージ ペイロードが含まれるかどうかが確認されます。 メッセージ コンテキストはこのパイプライン コンポーネントによって保存され、必要な BizTalk Framework プロパティを生成した上で、新しいメッセージ コンテキストが作成されます。 このプロパティは、処理の対象となるメッセージを BizTalk Framework の受信ハンドラーにルーティングする際に使用されます。  
  
 BizTalk Framework 逆アセンブラー パイプライン コンポーネントは、送信元から送られてきた BizTalk Framework エンベロープ内の deliverReceiptRequest ヘッダーを見て、必要に応じて、生成されたメッセージの受信確認を生成します。 これは、BizTalk Framework アセンブラー パイプライン コンポーネントの配信確認メッセージ要求の生成プロパティによって制御されます。 BizTalk フレームワークの詳細については、次を参照してください。 [BizTalk Framework アセンブラー パイプライン コンポーネント](../core/biztalk-framework-assembler-pipeline-component.md)です。  
  
 BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成して、オーケストレーションの作成については、次を参照してください。 [BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)   
 [パイプライン コンポーネント](../core/pipeline-components.md)