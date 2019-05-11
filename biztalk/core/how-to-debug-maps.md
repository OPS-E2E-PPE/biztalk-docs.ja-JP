---
title: マップをデバッグする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1ee1e26-fced-4126-b48a-71007043424d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9459cc2d2d51347e508ac989a9aeb54b9ac1059d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338888"
---
# <a name="how-to-debug-maps"></a>マップをデバッグする方法
**マップのデバッグ**識別および複雑なマッピングの問題を修正する便利な機能です。 このトピックでは、インライン XSLT デバッガーを使用してマップをデバッグするための詳細な手順を説明します。  

> [!NOTE]
>  マップをデバッグするときに、**マップのデバッグ**機能は、マップ ファイルのプロパティを使用して**TestMap の入力インスタンス**と**TestMap 出力インスタンス**します。 そのため、マップをデバッグする前に、入力を構成し、マップ ファイルにインスタンスのプロパティを出力することを勧めします。  

### <a name="to-debug-a-biztalk-map"></a>BizTalk マップをデバッグするには  

1. ソリューション エクスプ ローラーで、テスト、およびクリックするマップを右クリックして**マップのデバッグ**します。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] エディターで XSLT 形式で、マップを表示します。  

2. XSL コードをデバッグするには、f10 キーまたは F11 キーを押します。 Functoid の呼び出しで f11 キーを押す[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]にステップ イン、 C# 、functoid のコード。 ローカル Windows デバッガーで functoid のソース コードで使用される変数の値を表示することができます。
