---
title: 環境の設定 |Microsoft Docs
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
ms.openlocfilehash: c2bcff19cb26482c566820956f93642887b43015
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530095"
---
# <a name="setting-the-environment"></a><span data-ttu-id="02dcb-102">環境の設定</span><span class="sxs-lookup"><span data-stu-id="02dcb-102">Setting the Environment</span></span>
<span data-ttu-id="02dcb-103">**環境を設定します。**</span><span class="sxs-lookup"><span data-stu-id="02dcb-103">**To set the environment:**</span></span>  
  
1.  <span data-ttu-id="02dcb-104">SWIFT メッセージ パックが構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="02dcb-104">Make sure SWIFT Message Pack is configured.</span></span> <span data-ttu-id="02dcb-105">同じ構成に Swift メッセージ パックのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02dcb-105">Refer to the Swift Message Pack documentation to configure the same.</span></span>  
  
2.  <span data-ttu-id="02dcb-106">SQL スクリプトを実行*\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\CreateProceduresScript.sql します。</span><span class="sxs-lookup"><span data-stu-id="02dcb-106">Run the SQL script *\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\CreateProceduresScript.sql.</span></span> <span data-ttu-id="02dcb-107">Swift および MessagePack は A4Swift 以外のデータベース名で構成されている場合は、sql スクリプト内のデータベース名を変更します。</span><span class="sxs-lookup"><span data-stu-id="02dcb-107">Change the database name in the sql script if the Swift and MessagePack are configured for database name other than A4Swift.</span></span>  
  
3.  <span data-ttu-id="02dcb-108">コンピューター名とデータベース名として"database"キーとして「データ ソース」のキーの値を設定 (を Swift および MessagePack が構成されている) ファイルに*\<ドライブ\>*: \Program Files\Microsoft BizTalkSWIFT\SDK\Tools\DataImport\DataImport.exe.config のアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="02dcb-108">Set the value of Key “datasource” as ComputerName and key “database” as database name (for which the Swift and MessagePack is configured) in the file *\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\DataImport.exe.config.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="02dcb-109">データの入力ファイルは、DataImport.exe ファイルと同じフォルダーにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="02dcb-109">The data input file should not be in the same folder as the DataImport.exe file.</span></span>  
  
4.  <span data-ttu-id="02dcb-110">BICplusIBAN と SEPA テーブル内のデータをインポートするデータ インポート ユーティリティを実行します。</span><span class="sxs-lookup"><span data-stu-id="02dcb-110">Run the DataImport utility to import data in BICplusIBAN and SEPA tables.</span></span>