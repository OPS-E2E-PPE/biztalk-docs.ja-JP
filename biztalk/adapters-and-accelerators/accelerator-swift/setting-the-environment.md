---
title: 環境の設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43027efc-acec-4110-96bd-cc4a19daaeab
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f0c63671833a394e0c750561d90c12c6476515f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961896"
---
# <a name="setting-the-environment"></a><span data-ttu-id="4756e-102">環境の設定</span><span class="sxs-lookup"><span data-stu-id="4756e-102">Setting the Environment</span></span>
<span data-ttu-id="4756e-103">**環境を設定します。**</span><span class="sxs-lookup"><span data-stu-id="4756e-103">**To set the environment:**</span></span>  
  
1.  <span data-ttu-id="4756e-104">SWIFT メッセージ パックが構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4756e-104">Make sure SWIFT Message Pack is configured.</span></span> <span data-ttu-id="4756e-105">同じ構成に Swift メッセージ パックのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4756e-105">Refer to the Swift Message Pack documentation to configure the same.</span></span>  
  
2.  <span data-ttu-id="4756e-106">SQL スクリプトを実行*\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\CreateProceduresScript.sql です。</span><span class="sxs-lookup"><span data-stu-id="4756e-106">Run the SQL script *\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\CreateProceduresScript.sql.</span></span> <span data-ttu-id="4756e-107">Swift および MessagePack が A4Swift 以外のデータベース名に対して構成されている場合は、sql スクリプトのデータベース名を変更します。</span><span class="sxs-lookup"><span data-stu-id="4756e-107">Change the database name in the sql script if the Swift and MessagePack are configured for database name other than A4Swift.</span></span>  
  
3.  <span data-ttu-id="4756e-108">コンピューター名とキー データベース名として"database"キー「データ ソース」の値を設定 (対象の Swift および MessagePack が構成されている) ファイルに*\<ドライブ\>*: \Program Files\Microsoft BizTalkSWIFT\SDK\Tools\DataImport\DataImport.exe.config のアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="4756e-108">Set the value of Key “datasource” as ComputerName and key “database” as database name (for which the Swift and MessagePack is configured) in the file *\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\DataImport.exe.config.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4756e-109">データの入力ファイルは、DataImport.exe ファイルと同じフォルダーにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4756e-109">The data input file should not be in the same folder as the DataImport.exe file.</span></span>  
  
4.  <span data-ttu-id="4756e-110">BICplusIBAN と SEPA テーブル内のデータをインポートするインポート ユーティリティを実行します。</span><span class="sxs-lookup"><span data-stu-id="4756e-110">Run the DataImport utility to import data in BICplusIBAN and SEPA tables.</span></span>