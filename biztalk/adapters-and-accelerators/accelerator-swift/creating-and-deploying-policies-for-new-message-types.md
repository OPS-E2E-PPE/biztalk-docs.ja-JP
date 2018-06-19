---
title: 新しいポリシーの展開の作成とメッセージの種類 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43343238-ec45-44ed-a230-9e234bd22d05
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b826b3ee9408caf91fe5adcb2177d709f885a6e1
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25966312"
---
# <a name="creating-and-deploying-policies-for-new-message-types"></a><span data-ttu-id="0b0ac-102">作成して、新しいメッセージの種類のポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-102">Creating and Deploying Policies for New Message Types</span></span>
<span data-ttu-id="0b0ac-103">作成して、新しいメッセージの種類のポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-103">To create and deploy policies for new message types:</span></span>  
  
1.  <span data-ttu-id="0b0ac-104">MX メッセージ フォルダー内のメッセージの種類の名前を持つフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-104">Create a folder with the name of the message type inside MX Messages folder.</span></span> <span data-ttu-id="0b0ac-105">たとえば、ここでは、フォルダーの名前になります setr.004.001.02 です。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-105">For example, in this case the name of the folder would be setr.004.001.02.</span></span>  
  
    ```csharp  
    (<xs:complexType name="Document">  
        <xs:sequence>  
            <xs:element name="setr.004.001.02" type="setr.004.001.02"/>  
        </xs:sequence>  
    </xs:complexType>)  
    ```  
  
2.  <span data-ttu-id="0b0ac-106">結果として得られるマスターと共にスキーマ ファイル (\*.xsd) 配置検証ポリシーは、このフォルダーにこのメッセージの種類のファイルです。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-106">Place the schema file (\*.xsd) along with the resulting master / validation policy file for this message type in this folder.</span></span>  
  
3.  <span data-ttu-id="0b0ac-107">キーワードの名前を持つ MXMessageTypeKeywordList.xml (C:\Program files \microsoft BizTalk Accelerator for swift \sdk\tools) を更新します。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-107">Update the MXMessageTypeKeywordList.xml (C:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools) with a keyword name.</span></span> <span data-ttu-id="0b0ac-108">この名前は、メッセージのフォルダー名の最初の 4 つの文字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-108">This name must be the first four letters of the message folder name.</span></span> <span data-ttu-id="0b0ac-109">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-109">For example,</span></span>  
  
    ```csharp  
    (<Keyword name ="setr" />)  
    ```  
  
4.  <span data-ttu-id="0b0ac-110">特定のマスターを作成する検証ポリシーには、master データベースのコピー//検証ポリシー ファイル、既存のメッセージし、新しいメッセージ フォルダーに配置します。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-110">To create specific master / validation policies, take a copy of the master / validation policy files of the existing message and place it in the new message folder.</span></span>  
  
5.  <span data-ttu-id="0b0ac-111">マスターのメッセージの種類への参照のすべての変更/新しいメッセージの種類を反映するようにポリシーを検証します。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-111">Change all of the references to message types in the master / validation policy to reflect the new message types.</span></span>  
  
## <a name="message-naming-conventions"></a><span data-ttu-id="0b0ac-112">メッセージの名前付け規則</span><span class="sxs-lookup"><span data-stu-id="0b0ac-112">Message Naming Conventions</span></span>  
 <span data-ttu-id="0b0ac-113">これらのメッセージ名の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-113">Follow these conventions for message names:</span></span>  
  
-   <span data-ttu-id="0b0ac-114">**メッセージ名に読み替え**: 新しいメッセージ名が swift.if.ia.setr.004.001.02 ポリシー ファイルが使用されている古いメッセージが pacs.002.001.02 の場合、[すべて置換] と pacs.002.001.02 の出現回数のポリシー ファイル内で swift.if.ia.setr.004.001.02 です。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-114">**Replacing the message name**: If the new message name is swift.if.ia.setr.004.001.02 and the old message whose policy files have been used is pacs.002.001.02, then replace all of the occurrences of pacs.002.001.02 with swift.if.ia.setr.004.001.02 within the policy files.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0b0ac-115">メッセージ名はダウンロードされて、スキーマ ファイルの名前であり、メッセージの種類は、メッセージ内のドキュメントの種類の名前です。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-115">Message name is the name of the schema file which has been downloaded and message type is the name of the document type in the message.</span></span>  
  
-   <span data-ttu-id="0b0ac-116">メッセージ スキーマ自体と同じポリシー ファイルの名前を保持します。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-116">Keep the name of the policy files the same as the message schema itself.</span></span> <span data-ttu-id="0b0ac-117">たとえば、swift.if.ia.setr.004.001.02.xsd は、次のポリシー swift.if.ia.setr.004.001.02 _Master_Policy.xml と swift.if.ia.setr.004.001.02 _Validation_Policy.xml があります。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-117">For example, swift.if.ia.setr.004.001.02.xsd will have following policies swift.if.ia.setr.004.001.02 _Master_Policy.xml and swift.if.ia.setr.004.001.02 _Validation_Policy.xml.</span></span>  
  
-   <span data-ttu-id="0b0ac-118">**特殊文字**: メッセージ名が、特殊文字を持つかどうかは、ポリシー ファイルを作成すると、若干異なる規則が必要です。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-118">**Special characters**: If the message name has any special characters in it, then creating a policy file requires a slightly different convention.</span></span> <span data-ttu-id="0b0ac-119">メッセージ名は、たとえば、swift.if.ia$setr.004.001.02 かどうか、は、置き換えられる特殊文字を含むメッセージ名をポリシー ファイルの名前を変更する必要があります"です"。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-119">If the message name is, for example, swift.if.ia$setr.004.001.02, then you must change the name of the policy file to the message name with the special characters being replaced by “.”</span></span> <span data-ttu-id="0b0ac-120">たとえば、メッセージのスキーマ ファイルの名前が swift.if.ia$setr.004.001.02.xsd の場合は、結果として得られるマスター ポリシー swift.if.ia.setr.004.001.02_Master_Policy.xml はなります。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-120">For example, if the name of the message schema file is swift.if.ia$setr.004.001.02.xsd, then the resulting master policy would be swift.if.ia.setr.004.001.02_Master_Policy.xml.</span></span>  
  
     <span data-ttu-id="0b0ac-121">また、マスター ポリシー ファイルは、次のタグに新しい名前を反映するように変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b0ac-121">The master policy file also needs to be changed to reflect the new name in the following tags:</span></span>  
  
    -   <span data-ttu-id="0b0ac-122">\<ruleset name="swift.if.ia.setr.004.001.02_Master_Policy"\></span><span class="sxs-lookup"><span data-stu-id="0b0ac-122">\<ruleset name="swift.if.ia.setr.004.001.02_Master_Policy"\></span></span>  
  
    -   <span data-ttu-id="0b0ac-123">< name="swift.if.ia.setr.004.001.02_Policy_List のルール"</span><span class="sxs-lookup"><span data-stu-id="0b0ac-123"><rule name="swift.if.ia.setr.004.001.02_Policy_List"</span></span>