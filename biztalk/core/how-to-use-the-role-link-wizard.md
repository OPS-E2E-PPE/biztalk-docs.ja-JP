---
title: ロール リンク ウィザードを使用する方法 |Microsoft Docs
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
ms.openlocfilehash: 5336dcbb129b01be8fc03c43756bb1fc1ac53063
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333199"
---
# <a name="how-to-use-the-role-link-wizard"></a>ロール リンク ウィザードを使用する方法
ロール リンク ウィザードを使用すると、新しいロール リンクを作成または既存のものを変更できます。 設定または表示名、型、およびロール リンクだけでなく、実装ロールおよびロール リンクの種類を構成する使用ロールのアクセス制限を使用できます。 ロール リンクの機能については、次を参照してください。[オーケストレーションでロール リンクを使用して](../core/using-role-links-in-orchestrations.md)します。  
  
 **ロール リンク名**:ロール リンク名に入力してを構成している既存のロール リンクの現在の名前か、自動的に生成された名前は、新しいロール リンクを作成する場合。 いずれの場合も、名前を変更できます。  
  
 **ロール リンクの種類**:既存のロール リンクの種類を選択したり、新しく作成できます。 新規または既存のロール リンクの種類を構成しているかどうかは、オーケストレーションがサービスに参加する方法を指定できます。  
  
> [!NOTE]
>  ロール リンクを定義するため、既存のロール リンクの種類を使用できるように、ロール リンクを作成するには、ロール リンクの種類と関連付けられているポートの種類の前に作成することをお勧めします。 詳細については、次を参照してください。[オーケストレーションでロール リンクを作成する方法](../core/how-to-create-role-links-in-orchestrations.md)します。  
  
 **ロール リンクの使用法**:新しいロール リンクの種類を作成する場合、両方の実装と使用ロールが自動的に作成します。 オーケストレーションがサービスに参加する方法を反映するロールを選択できます。 ウィザードの手順を完了すると後、は、ロール識別子の名前変更または実装に合わせてロールを削除できます。 ロール リンクの種類には、いずれかのロールの種類のいずれかまたはロールの種類ごとの 1 つを含める必要があります。 クリックすると**OK**、それぞれの名前に対応する未構成のロールを作成します。 種類 ウィンドウで、ロールのポートの種類を選択することもできます。  
  
> [!NOTE]
>  ロール リンクの種類のポートの種類を作成し、以前に定義されたポートの種類を選択するには、ポート構成ウィザードを起動する場合は、ポートの種類のアクセス制限がロール リンクの種類のアクセス制限と競合しないことを確認します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションでのロール リンクの使用](../core/using-role-links-in-orchestrations.md)