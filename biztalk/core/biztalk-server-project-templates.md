---
title: Visual Studio プロジェクト テンプレート |Microsoft Docs
description: .Btproj、BPEL、および BizTalk Server で使用される .btaproj Visual Studio テンプレートについて説明します
ms.custom: ''
ms.date: 11/07/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2b3d494-db80-4314-afcd-d08d5a26e211
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 412ee949494d6009032ace80cbf082a979afb492
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357902"
---
# <a name="biztalk-server-project-templates"></a>BizTalk Server プロジェクト テンプレート

## <a name="overview"></a>概要
インストールするときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、インストールで追加する BizTalk プロジェクト フォルダー、**新しいプロジェクト** ダイアログ ボックス。 BizTalk Projects フォルダーには、空の BizTalk Server プロジェクト、BizTalk Server BPEL インポート プロジェクト、および BizTalk Server アプリケーション プロジェクトを作成するためのテンプレートが含まれています。

## <a name="available-templates"></a>使用可能なテンプレート
次の表では、これらのプロジェクト テンプレートについて説明します。  


|                     プロパティ                      |                                                                                                                                                                   目的                                                                                                                                                                   |
|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         **空の BizTalk Server プロジェクト**          |                                                                                                                                                  新しい空の BizTalk Server プロジェクトを作成します。                                                                                                                                                   |
|      **BizTalk Server BPEL インポート プロジェクト**       |                                                                                      Business Process Execution Language (BPEL)、Web サービス記述言語 (WSDL)、または XML スキーマ定義言語 (XSD) ファイルを BizTalk プロジェクトにインポートします。                                                                                       |
| **BizTalk Server アプリケーション プロジェクト (.btaproj)** | 以降で[!INCLUDE[bts2016](../includes/bts2016-md.md)] [Feature Pack 1](../core/configure-the-feature-pack.md)、またはそれ以降。 <br/><br/>自動的に展開して、Visual Studio Team Services (VSTS) を使用してアプリケーションを更新するために使用します。 プロジェクトに含まれる、`BizTalkServerInventory.json`展開中に VSTS によって使用されるファイル。 |

## <a name="see-also"></a>参照  
 [BizTalk プロジェクトの操作](../core/working-with-biztalk-projects.md)
