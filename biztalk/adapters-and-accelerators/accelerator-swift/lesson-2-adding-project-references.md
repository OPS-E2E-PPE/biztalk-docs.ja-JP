---
title: レッスン 2:プロジェクト参照の追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- references [projects]
- projects, adding references
ms.assetid: ddc2bf49-cddd-4edb-8043-870897879655
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c339baa026508cc520b96480a57e55dd6c86b915
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530356"
---
# <a name="lesson-2-adding-project-references"></a>レッスン 2:プロジェクト参照の追加
パイプライン Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll ファイル内にある既定の実行時のスキーマにアクセスできるように、プロジェクト参照を追加します。 このアセンブリ ファイルには、メッセージ型の解決に必要な昇格させたプロパティを持つヘッダー スキーマが含まれています。  
  
 逆アセンブル コンポーネントを受信パイプラインに追加するときに、ヘッダー スキーマを後で参照します。  
  
### <a name="to-add-a-reference-to-the-default-swift-runtimeschemas-assembly"></a>既定の SWIFT RuntimeSchemas アセンブリへの参照を追加するには  
  
1.  ソリューション エクスプ ローラーで、 **SWIFTPipelines**プロジェクトを展開します。 右クリック**参照**、 をクリックし、**参照の追加**します。  
  
2.  [参照の追加] ダイアログ ボックスで、**参照**タブ。  
  
3.  参照する **\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\Assemblies**します。  
  
4.  選択、 **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll**ファイル。  
  
5.  クリックして**追加**、順にクリックします**OK**します。  
  
    > [!NOTE]
    >  これで、選択した RuntimeSchemas アセンブリ (dll) は、SWIFTPipelines プロジェクト内の参照のコレクションが表示されます。  
  
#### <a name="to-add-a-reference-to-the-swiftpipelines-schemas-assembly"></a>SWIFTPipelines スキーマ アセンブリへの参照を追加するには  
  
1. ソリューション エクスプ ローラーで [、 **SWIFTPipelines**プロジェクトを右クリックして**参照**、] をクリックし、**参照の追加**。  
  
2. 参照の追加 ダイアログ ボックスで、上、**プロジェクト**タブをクリックし、 **SWIFTSchemas**プロジェクトで、をクリックして**追加**、順にクリックします**ok**。  
  
3. **ファイル** メニューのをクリックして**すべて保存**変更を保存します。  
  
   続行する[レッスン 3。カスタム受信パイプラインを追加する](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)します。