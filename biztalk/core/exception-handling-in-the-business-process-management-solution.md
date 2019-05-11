---
title: ビジネス プロセス管理ソリューションでの例外処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, tutorials
- process management solution tutorial, errors
ms.assetid: ac9fcb33-7dac-448e-88b8-04d4d439ea6a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d06209f49a4702397ea13407593d9286e1f31be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388311"
---
# <a name="exception-handling-in-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションでの例外処理
ビジネス プロセス管理ソリューションが特殊な例外処理のオーケストレーション、アダプタ、パイプライン、マッピングを標準の BizTalk Server 例外処理とを使用し、新しいエラー報告機能のルーティングのエラーにします。 このカスタマイズされたシステムを構築、 **ExceptionHandler**オーケストレーションします。 ソリューションを使用して、 **ExceptionHandler**オーケストレーション、操作を再試行するか、一時的な問題と成功する可能性の呼び出しを再試行してください。  
  
> [!NOTE]
>  など、オーケストレーションのコードを再利用できます**Activate**、使用する、 **ExceptionHandler**オーケストレーションします。 という名前のスコープは、これらのオーケストレーションのすべて**CallingCode**添付で**例外**ブロックします。 コードに置き換えます、 **CallingCode**コードを持つスコープ。 **例外**ブロックを呼び出す必要変数の定義、 **ExceptionHandler**オーケストレーションします。 変数に割り当てられた値を編集します。  
  
 ソリューションは、エラーが正しくない形式の注文メッセージなどの回復可能な場合、カスタム例外と定義済みのいくつかの BizTalk 例外を使用します。  
  
> [!NOTE]
>  ソリューションでは、いくつかのポート上の障害を処理するため、カスタム アダプターを使用します。 アダプターの詳細については、次を参照してください。 [、Ops アダプタ](../core/the-ops-adapter.md)します。  
  
 このセクションについて説明します、 **ExceptionHandler**オーケストレーションとカスタムの例外。 についても説明、簡単に、どのようにエラー報告機能を使用します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ExceptionHandler オーケストレーション](../core/the-exceptionhandler-orchestration.md)  
  
-   [カスタム例外](../core/custom-exceptions.md)