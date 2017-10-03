---
title: "ビジネス プロセス管理ソリューションでの例外処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, tutorials
- process management solution tutorial, errors
ms.assetid: ac9fcb33-7dac-448e-88b8-04d4d439ea6a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cd3134b8ed4e2fc6fd4a50d9b64397692ea32b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="exception-handling-in-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションでの例外処理
ビジネス プロセス管理ソリューションでは、標準の BizTalk Server 例外処理に加えて特殊な例外処理オーケストレーションを使用します。アダプタ、パイプライン、マッピング、およびルーティングのエラーには新しいエラー報告機能を使用します。 このカスタマイズされたシステムを構築、 **ExceptionHandler**オーケストレーションです。 ソリューションを使用して、 **ExceptionHandler**操作を再試行するか、一時的な問題の発生後に成功する可能性がありますの呼び出しを再試行するオーケストレーションです。  
  
> [!NOTE]
>  など、オーケストレーションのコードを再使用できる**Activate**、使用する、 **ExceptionHandler**オーケストレーションです。 という名前のスコープは、すべてこれらのオーケストレーションの**CallingCode**添付と**例外**ブロックします。 コードで置き換え、 **CallingCode**コードにスコープします。 **例外**ブロックには、すべてを呼び出す変数必要性を定義、 **ExceptionHandler**オーケストレーションです。 変数に指定されている値は編集することができます。  
  
 注文メッセージの形式が正しくない場合など、エラーが回復不可能である場合は、カスタム例外と定義済みの BizTalk 例外が使用されます。  
  
> [!NOTE]
>  ポートによっては、ポート エラーの処理にカスタム アダプタが使用される場合があります。 アダプターに関する詳細については、次を参照してください。 [、Ops アダプタ](../core/the-ops-adapter.md)です。  
  
 このセクションの内容について説明します、 **ExceptionHandler**オーケストレーションとカスタム例外です。 さらに、エラー報告機能がどのように使用されるかについても簡単に説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ExceptionHandler オーケストレーション](../core/the-exceptionhandler-orchestration.md)  
  
-   [カスタム例外](../core/custom-exceptions.md)