---
title: ロール リンク ウィザードを使用する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- links [roles]
- Role Link Wizard [Orchestration Designer]
- roles, links
- Orchestration Designer, Role Link Wizard
- role links, Role Link Wizard [Orchestration Designer]
- links [roles], about links
ms.assetid: ddc33d87-c08d-4193-9483-4644ef302853
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d31abcc8fcc2bfaf1ebd641e1e52ad08d1c9c9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255858"
---
# <a name="how-to-use-the-role-link-wizard"></a>ロール リンク ウィザードを使用する方法
ロール リンク ウィザードを使用すると、新しいロール リンクの作成や既存のロール リンクの変更を行うことができます。 ロール リンク ウィザードでは、ロール リンクの種類を構成する使用ロールと実装ロール、およびロール リンクについて、名前、種類、アクセス制限の設定や表示を行うことができます。 ロール リンクの機能を理解するのを参照してください。[オーケストレーションでロール リンクを使用して](../core/using-role-links-in-orchestrations.md)です。  
  
 **ロール リンク名**: ロール リンク名に入力して、新しいロール リンクを作成する場合は、現在の名前を構成している既存のロール リンクか、自動的に生成された名前は、します。 どちらの場合も名前を変更できます。  
  
 **ロール リンクの種類**: 既存のロール リンクの種類を選択または新規に作成できます。 ロール リンクの種類が新規または既存のどちらで構成されていても、オーケストレーションがサービスに参加する方法を指定できます。  
  
> [!NOTE]
>  ロール リンクを作成する前にロール リンクの種類を作成してポートの種類を関連付け、既存のロール リンクの種類をロール リンクの定義に使用できるようにしておくことをお勧めします。 詳細については、次を参照してください。[オーケストレーションでロール リンクを作成する方法](../core/how-to-create-role-links-in-orchestrations.md)です。  
  
 **ロール リンクの使用法**: 新しいロール リンクを作成する場合、両方の実装を入力し、使用して役割が自動的に作成します。 オーケストレーションがサービスに参加する方法を表すロールを選択できます。 ウィザードの手順を完了すると、実装に合わせてロールの識別子の名前を変更したり、ロールを削除したりすることができます。 ロール リンクの種類には、いずれかのロールの種類を 1 つ、または各ロールの種類を 1 つずつ含める必要があります。 クリックすると、 **OK**、未構成の役割が作成される各名前に対応します。 また、[種類] ウィンドウではロールのポートの種類を選択できます。  
  
> [!NOTE]
>  ポート構成ウィザードを呼び出してロール リンクの種類に対するポートの種類を作成する際に、以前定義したポートの種類を選択する場合、ポートの種類のアクセス制限がロール リンクの種類のアクセス制限と競合していないことを確認してください。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションでロール リンクの使用](../core/using-role-links-in-orchestrations.md)