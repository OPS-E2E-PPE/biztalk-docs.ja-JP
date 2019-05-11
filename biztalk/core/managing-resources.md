---
title: リソースの管理 |Microsoft Docs
description: Btstask または BizTalk 管理コンソールを使用して、アセンブリ、スクリプト、証明書、バインド ファイル、および BizTalk Server で複数の操作
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b478ef2e-1363-4c2c-a4b7-6a582a6b33a5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a26a0afc6832dfa4c8401442dc000262dab3aec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380221"
---
# <a name="manage-resources"></a>リソースを管理します。

## <a name="overview"></a>概要
ここでは、BizTalk グループに BizTalk Server リソースを展開した後、BizTalk Server 管理コンソールまたは BTSTask コマンドライン ツールを使用して BizTalk Server リソースを管理する方法について説明します。 リソースには、次の種類のアイテムが含まれます。  
  
-   BizTalk アセンブリ  
  
-   処理前および処理後のスクリプト  
  
-   .NET アセンブリ  
  
-   COM コンポーネント  
  
-   証明書  
  
-   アドホック ファイル  
  
-   BAM 定義  
  
-   バインド ファイル  
  
-   仮想ディレクトリ  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
> 
> [!NOTE]
>  どのような場合においても、同じ名前の複数のリソースを BizTalk Server グループに追加しないでください。 BizTalk Server 管理データベースの格納先 SQL Server の構成で、バイナリ照合順序が使用され、大文字と小文字の区別がサポートされている場合でも、同じ名前の複数のリソースを BizTalk Server グループに追加することはできません。  
  
## <a name="next-steps"></a>次のステップ
  
-   [BizTalk アセンブリの管理](../core/managing-biztalk-assemblies.md)  
  
-   [処理前および処理後のスクリプトの管理](../core/managing-pre-and-post-processing-scripts.md)  
  
-   [.NET アセンブリ、証明書、およびその他のリソースの管理](../core/managing-net-assemblies-certificates-and-other-resources.md)  
  
-   [リソースの更新](../core/how-to-refresh-a-resource.md)