---
title: BizTalk Framework 逆アセンブラー パイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Disassembler
- BizTalk Framework Disassembler [pipeline component]
ms.assetid: 48d6c530-5c02-4c70-ad11-0ea6c3c808f8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36269df0c1b93ca68ffeb41d78742e926af14c92
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358052"
---
# <a name="biztalk-framework-disassembler-pipeline-component"></a>BizTalk Framework 逆アセンブラー パイプライン コンポーネント
BizTalk Framework 逆アセンブラー パイプライン コンポーネントは、XML データを解析し、BizTalk Framework ベースのメッセージング ペイロードが含まれているかどうかを決定します。 パイプライン コンポーネントが、メッセージ コンテキストを保存しを生成する必要がある BizTalk Framework プロパティを使用して、新しいメッセージ コンテキストを作成します。 このプロパティは、BizTalk Framework の受信ハンドラーに処理するメッセージを受信できるようにメッセージをルーティングに使用されます。  
  
 BizTalk Framework 逆アセンブラー パイプライン コンポーネントは、1 つに、BizTalk Framework エンベロープ内の deliverReceiptRequest ヘッダーを使用して、送信側が要求された場合に生成されたメッセージの受信確認を生成します。 これは、BizTalk Framework アセンブラー パイプライン コンポーネントで生成配信確認メッセージのプロパティによって制御されます。 BizTalk フレームワークの詳細については、次を参照してください。 [BizTalk Framework アセンブラー パイプライン コンポーネント](../core/biztalk-framework-assembler-pipeline-component.md)します。  
  
 BizTalk Framework 逆アセンブラー パイプライン コンポーネントの構成およびオーケストレーションの作成については、次を参照してください。 [BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)   
 [パイプライン コンポーネント](../core/pipeline-components.md)