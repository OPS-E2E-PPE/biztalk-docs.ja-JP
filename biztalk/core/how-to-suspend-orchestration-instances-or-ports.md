---
title: オーケストレーションのインスタンスまたはポートを中断する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, suspending
- instances, suspending
- suspending
- HAT, suspending orchestrations
- HAT, suspending pipelines
- suspending, ports
- suspending, orchestrations
- orchestrations, suspending
- HAT, suspending ports
- suspending, instances
- ports, suspending
ms.assetid: cacc7e58-7d3e-4d6b-adb0-618fdc4f0d89
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62d91c8d1e02b7283a430f7c82c572b6a989d108
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22256698"
---
# <a name="how-to-suspend-orchestration-instances-or-ports"></a>オーケストレーションのインスタンスまたはポートを中断する方法
BizTalk Server 管理コンソールのクエリ結果一覧から、オーケストレーションのインスタンスまたはポートを中断できます。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行する BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-suspend-orchestration-instances-or-ports"></a>オーケストレーションのインスタンスまたはポートを中断するには  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**, 、し、BizTalk グループ をクリックします。  
  
3.  詳細ペインでクリックして、 **新しいクエリ**  タブをクリックします。  
  
4.  **クエリ式** グループの **値** 列で、選択 **サービス インスタンスを実行している** ドロップダウン リスト ボックスからです。  
  
5.  次のいずれかの操作を行います。  
  
    -   単一のインスタンスを中断する、 **フィールド名** 列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***) を選択、 **サービス名** フィルターし、次に、 **値**  列で、サービス名を指定します。  
  
    -   インスタンスをまとめてを中断する、 **フィールド名** 列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***) を選択 **結果をグループ化** し、次に、 **値**  列で、サービス名を指定します。  
  
6.  クリックして **クエリを実行**します。  
  
7.  クエリ結果の一覧で、中断、およびをクリックするアクティブなオーケストレーションまたはポートを右クリックして **インスタンスの中断** または **インスタンスの中断**します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション、ポート、およびメッセージのエラーの調査](../core/investigating-orchestration-port-and-message-failures.md)