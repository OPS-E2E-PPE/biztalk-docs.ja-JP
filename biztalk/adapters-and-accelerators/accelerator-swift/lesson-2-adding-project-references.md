---
title: "レッスン 2: プロジェクト参照の追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- references [projects]
- projects, adding references
ms.assetid: ddc2bf49-cddd-4edb-8043-870897879655
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b00fc7d49024cec6f9c300444646da82069e16cc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-2-adding-project-references"></a>レッスン 2: プロジェクト参照の追加
プロジェクト参照を追加する、パイプライン Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll ファイル内にある既定の実行時のスキーマにアクセスできるようにします。 このアセンブリ ファイルには、メッセージ型の解決に必要な昇格させたプロパティを持つヘッダー スキーマが含まれています。  
  
 逆アセンブル コンポーネントを受信パイプラインに追加するときに、ヘッダー スキーマを後で参照します。  
  
### <a name="to-add-a-reference-to-the-default-swift-runtimeschemas-assembly"></a>既定の SWIFT RuntimeSchemas アセンブリへの参照を追加するには  
  
1.  ソリューション エクスプ ローラーでいることを確認、 **SWIFTPipelines**プロジェクトを展開します。 右クリック**参照**、クリックして**参照の追加**です。  
  
2.  [参照の追加] ダイアログ ボックス、**参照**タブです。  
  
3.  参照  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\Assemblies * *。  
  
4.  選択、 **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll**ファイル。  
  
5.  をクリックして**追加**、順にクリック**OK**です。  
  
    > [!NOTE]
    >  これで、選択した RuntimeSchemas アセンブリ (dll) は、コレクション SWIFTPipelines プロジェクト内の参照が表示されます。  
  
#### <a name="to-add-a-reference-to-the-swiftpipelines-schemas-assembly"></a>SWIFTPipelines スキーマ アセンブリへの参照を追加するには  
  
1.  ソリューション エクスプ ローラーで、、 **SWIFTPipelines**プロジェクトを右クリックして**参照**、順にクリック**参照の追加**です。  
  
2.  参照の追加 ダイアログ ボックスで、**プロジェクト** タブで、をクリックして、 **SWIFTSchemas**プロジェクトで、をクリックして**追加**、順にクリック**ok**です。  
  
3.  **ファイル** メニューのをクリックして**すべて保存**して変更を保存します。  
  
 進みます[レッスン 3: カスタム受信パイプラインを追加する](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)です。